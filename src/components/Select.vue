
<script setup lang="ts">
import { ref } from "vue";
import VueSelect from "vue3-select-component";

const options = [
      { label: 'Option #1', value: 'option_1' },
      { label: 'Option #2', value: 'option_2' },
      { label: 'Option #3', value: 'option_3' },
    ];

const selected = ref("");


function select(option) {
 console.log("*** selected:", option.value, selected.value)

}

</script>

<template>
  <VueSelect
    v-model="selected"
    :options="options"
    placeholder="Select an option"

    @option-selected="select"
  />
</template>

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
