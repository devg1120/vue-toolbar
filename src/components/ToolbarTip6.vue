<script setup lang="ts">

import { ref , defineEmits} from 'vue';
//import VueDatePicker from '@vuepic/vue-datepicker';
//import '@vuepic/vue-datepicker/dist/main.css'
import { CalendarIcon } from './@heroicons/vue/24/outline'
import { TrashIcon } from './@heroicons/vue/24/outline'
import { XMarkIcon } from './@heroicons/vue/24/outline'
import { Square2StackIcon } from './@heroicons/vue/24/outline'
import { RectangleGroupIcon  } from './@heroicons/vue/24/outline'
import { PlusIcon  } from './@heroicons/vue/24/outline'
import { MinusIcon  } from './@heroicons/vue/24/outline'
import { PencilSquareIcon  } from './@heroicons/vue/24/outline'
import { PaperAirplaneIcon  } from './@heroicons/vue/24/outline'
import { PaperClipIcon  } from './@heroicons/vue/24/outline'
import { ArrowPathIcon  } from './@heroicons/vue/24/outline'
import { ArrowUturnRightIcon  } from './@heroicons/vue/24/outline'
import { ArrowUturnLeftIcon  } from './@heroicons/vue/24/outline'
import { ArrowsPointingOutIcon  } from './@heroicons/vue/24/outline'
import { ArrowsPointingInIcon  } from './@heroicons/vue/24/outline'
import { Cog6ToothIcon  } from './@heroicons/vue/24/outline'

import { EllipsisVerticalIcon } from './@heroicons/vue/24/outline'
import { EllipsisHorizontalIcon } from './@heroicons/vue/24/outline'
import { DocumentIcon } from './@heroicons/vue/24/outline'

import ToolbarItem6  from './ToolbarItem6.vue'


//import { CalendarIcon } from './@heroicons/vue/16/solid'

const props = defineProps(['toolbar_define']);

const emit = defineEmits(['toolbarItemClick']);


function indvisualHandler( name ) {
    for ( let x = 0; x < props.toolbar_define.length ; x++) {
         //console.log(props.toolbar_define[x].name)
	 if (props.toolbar_define[x].name == name) {
	    if (props.toolbar_define[x].indhandler) {
	         return true
            } else {
	    }
	 }
    }
    return false;
}
function handler( data ) {
   let i = indvisualHandler( name ) ;

   console.log("Click handler :", data, i);
   emit('toolbarItemClick', data)
}


</script>

<template>
<div class="toolbar-base">

 <template v-for="item in props.toolbar_define" v-bind:key="item">
	 <ToolbarItem6  :tooltip="item.tooltip"  :name="item.name" :alignright="item.alignright" @toolbarItemClick="handler"  > 
      <component v-bind:is="item.icon"  class="icon" :class="{ leftspace : item.leftspace, toggle : item.toggle   }"/>
      </ToolbarItem6>
</template>

	</div>
</template>
<style scoped>

.toolbar-base {
  display:flex;
  margin-left: 0px;
  margin-right: 0px;
  padding-left:10px;
  padding-right:10px;
  /* background-color: #f5f5f5;*/
}

.icon {
 width : 22px;
 height : 22px;
 cursor: pointer;
 margin: 3px 2px;
 padding: 3px 4px;
 box-shadow: 2px 2px 0px 0 lightgray;
}
 
.icon.mouse-down{
 box-shadow: -2px -2px 0px 0px lightgray;
}

.leftspace {
 margin-left: 20px;

}
/*
.alignright{

  margin-left: auto;

}
*/
</style>
