
<script setup lang="ts">
import { ref } from "vue";
import VueSelect from "vue3-select-component";

import { PaperAirplaneIcon  } from './@heroicons/vue/24/outline'

const options = [
      { label: 'Option #1' , value: 'option_1' },
      { label: 'Option #2' , value: 'option_2' },
      { label: 'Option #3' , value: 'option_3' },
      { label: 'Option #4' , value: 'option_4' },
      { label: 'Option #5' , value: 'option_5' },
      { label: 'Option #6' , value: 'option_6' },
      { label: 'Option #7' , value: 'option_7' },
      { label: 'Option #8' , value: 'option_8' },
      { label: 'Option #9' , value: 'option_9' },
      { label: 'Option #10', value: 'option_10' },
      { label: 'Option #11', value: 'option_11' },
      { label: 'Option #12', value: 'option_12' },
      { label: 'Option #13', value: 'option_13' },
      { label: 'Option #14', value: 'option_14' },
      { label: 'Option #15', value: 'option_15' },
      { label: 'Option #16', value: 'option_16' },
    ];
const options2 = [
      { label: PaperAirplaneIcon, value: 'option_4' },
      { label: PaperAirplaneIcon, value: 'option_4' },
      { label: PaperAirplaneIcon, value: 'option_4' },
    ];

const selected = ref("");


function select(option) {
 console.log("*** selected:", option.value, selected.value)

}

const styles = [
 "background-color:white",
 "background-color:silver",
 "background-color:gray",
 "background-color:black",

 "background-color:red",
 "background-color:maroon",
 "background-color:yellow",
 "background-color:olive",

 "background-color:lime",
 "background-color:green",
 "background-color:aqua",
 "background-color:teal",

 "background-color:blue",
 "background-color:navy",
 "background-color:fuchsia",
 "background-color:purple",
 ]


const styles_old = [
 "width:30px;background-color:white",
 "width:30px;background-color:silver",
 "width:30px;background-color:gray",
 "width:30px;background-color:black",

 "width:30px;background-color:red",
 "width:30px;background-color:maroon",
 "width:30px;background-color:yellow",
 "width:30px;background-color:olive",

 "width:30px;background-color:lime",
 "width:30px;background-color:green",
 "width:30px;background-color:aqua",
 "width:30px;background-color:teal",

 "width:30px;background-color:blue",
 "width:30px;background-color:navy",
 "width:30px;background-color:fuchsia",
 "width:30px;background-color:purple",
 ]
</script>

<!--
<template>
  <VueSelect
    v-model="selected"
    :options="options"
    placeholder="Select an option"

    @option-selected="select"
  />
</template>
-->

<!--
https://vue3-select-component.vercel.app/slots.html
-->

<template>
  <VueSelect v-model="selected" :options="options"
    placeholder="Select2"
    @option-selected="select"
    class="abc"
  >
    <template #option="{ option, index }"  >
	    <div :style="styles[index]" class="item" >&ensp;&ensp;&ensp;</div>
    </template>
  </VueSelect>;
</template>

<!--
<template>
  <VueSelect v-model="selected" :options="options"
    placeholder="Select2"
    @option-selected="select"
  >
    <template #option="{ option, index }">
      {{ option.label }} - {{ index }}
    </template>
  </VueSelect>
</template>
-->
<!--
<template>
  <VueSelect v-model="selected" :options="options"
    placeholder="Select an option"
    @option-selected="select"
  >
    <template #option="{ option, index }">
       <PaperAirplaneIcon/>
    </template>
  </VueSelect>
</template>
-->
<!--
<script setup lang="ts">
import type { Option } from "vue3-select-component";
import { ref } from "vue";
import VueSelect from "vue3-select-component";

type UserOption = Option<number> & { username: string };

const selectedUser = ref<number>();

const userOptions: UserOption[] = [
  { label: "Alice", value: 1, username: "alice15" },
  { label: "Bob", value: 2, username: "bob01" },
  { label: "Charlie", value: 3, username: "charlie20" },
];
</script>

<template>
  <VueSelect
    v-model="selectedUser"
    :options="userOptions"
    :get-option-label="(option) => `${option.label} (${option.username})`"
    placeholder="Pick a user"
  />
</template>
-->

<style scoped>
/*
:deep(.item) {
   width:160px !important;
}
*/
:deep(.menu) {
  display: grid;
/*
  width: 150px !important;
  grid-template-columns: repeat(auto-fill, minmax(30px, 1fr));

  width: 170px !important;
  grid-template-columns: repeat(auto-fill, minmax(35px, 1fr));
*/
  width: 180px !important;
  grid-template-columns: repeat(auto-fill, minmax(37px, 1fr));
}

/*
:deep(.menu) {
display:flex;
width: 200px !important;
flex-wrap: wrap;
}

:deep(.menu) > * {
  flex: 1 1 0px;
}
*/
</style>
