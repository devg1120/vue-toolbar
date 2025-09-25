<script setup lang="ts">
//import HelloWorld from './components/HelloWorld.vue'
import Toolbar from './components/Toolbar.vue'
import ToolbarTip from './components/ToolbarTip.vue'
import ToolbarTip2 from './components/ToolbarTip2.vue'
import ToolbarTip3 from './components/ToolbarTip3.vue'
import ToolbarTip4 from './components/ToolbarTip4.vue'
import ToolbarTip5 from './components/ToolbarTip5.vue'
import ToolbarTip6 from './components/ToolbarTip6.vue'


import { CalendarIcon } from './components/@heroicons/vue/24/outline'
import { TrashIcon } from    './components/@heroicons/vue/24/outline'
import { XMarkIcon } from    './components/@heroicons/vue/24/outline'
import { Square2StackIcon } from       './components/@heroicons/vue/24/outline'
import { RectangleGroupIcon  } from    './components/@heroicons/vue/24/outline'
import { PlusIcon  } from              './components/@heroicons/vue/24/outline'
import { MinusIcon  } from             './components/@heroicons/vue/24/outline'
import { PencilSquareIcon  } from      './components/@heroicons/vue/24/outline'
import { PaperAirplaneIcon  } from     './components/@heroicons/vue/24/outline'
import { PaperClipIcon  } from         './components/@heroicons/vue/24/outline'
import { ArrowPathIcon  } from         './components/@heroicons/vue/24/outline'
import { ArrowUturnRightIcon  } from   './components/@heroicons/vue/24/outline'
import { ArrowUturnLeftIcon  } from    './components/@heroicons/vue/24/outline'
import { ArrowsPointingOutIcon  } from './components/@heroicons/vue/24/outline'
import { ArrowsPointingInIcon  } from  './components/@heroicons/vue/24/outline'
import { Cog6ToothIcon  } from         './components/@heroicons/vue/24/outline'

import { EllipsisVerticalIcon } from   './components/@heroicons/vue/24/outline'
import { EllipsisHorizontalIcon } from './components/@heroicons/vue/24/outline'
import { DocumentIcon } from           './components/@heroicons/vue/24/outline'


function clickA( data ) {

   console.log("*************** Click A:", data);
   //alert("Click A");
}

function clickB( data ) {

   console.log("*************** Click B:", data);
   //alert("Click B");
}

const handler_define = [
  "clickA",
  "clickB",
];

const toolbar_define = [

{ icon : ArrowUturnRightIcon,
  name : "ArrowUturnRightIcon",
  handler : "clickA",
  tooltip : "A         OK",
},
{ icon : ArrowUturnLeftIcon,
  name : "ArrowUturnLeftIcon",
  tooltip : "B         OK",
  handler : "clickB",
},
{ icon : RectangleGroupIcon,
  name : "RectangleGroupIcon",
  tooltip : "B         OK",
},
{ icon : Square2StackIcon,
  name : "Square2StackIcon",
  tooltip : "B         OK",
},
{ icon : CalendarIcon,
  name : "CalendarIcon",
  leftspace : true,
  tooltip : "B         OK",
},
{ icon : TrashIcon,
  name : "TrashIcon",
  //leftspace : true,
  toggle : true,
  tooltip : "B         OK",
},
{ icon :XMarkIcon ,
  name : "XMarkIcon",
  tooltip : "B         OK",
},
{ icon : PlusIcon,
  name : "PlusIcon",
  tooltip : "B         OK",
},
{ icon : MinusIcon,
  name : "MinusIcon",
  tooltip : "B         OK",
},


{ icon : PencilSquareIcon,
  name : "PencilSquareIcon",
  leftspace: true,
  tooltip : "B         OK",
},

{ icon : PaperAirplaneIcon,
  name : "PaperAirplaneIcon",
  tooltip : "B         OK",
},
{ icon : PaperClipIcon,
  name : "PaperClipIcon",
  tooltip : "B         OK",
},

/*
  <ArrowsPointingOutIcon class="icon" />
  <ArrowsPointingInIcon class="icon" />
  <ArrowPathIcon class="icon" />
  <DocumentIcon class="icon" />
*/

{ icon : EllipsisVerticalIcon,
  name : "EllipsisVerticalIcon",
  alignright: true,
  tooltip : "B         OK",
},
{ icon : EllipsisHorizontalIcon,
  name : "EllipsisHorizontalIcon",
  tooltip : "B         OK",
},
{ icon : Cog6ToothIcon,
  name : "Cog6ToothIcon",
  tooltip : "B         OK",
},
];

function toolbarItemClick(data) {
  console.log(" App toolbar click:", data);


}
function toolbarItemToggle(data, state) {
  console.log(" App toolbar toggle:", data, state);


}
</script>

<template>

<div>
	<p> "Toolbar" toolbar</p>
  <Toolbar />
</div>
<div>
	<p> "ToolbarTip" tooltip and emit</p>
  <ToolbarTip />
</div>

<div>
	<p> "ToolbarTip2" dynamic item</p>
  <ToolbarTip2 />
</div>

<div>
	<p> "ToolbarTip3" for dynamic item</p>
  <ToolbarTip3 :toolbar_define="toolbar_define"  @toolbarItemClick="toolbarItemClick" />
</div>

<div>
	<p> "ToolbarTip4" for dynamic item  leftspace & toggle </p>
  <ToolbarTip4 :toolbar_define="toolbar_define"  @toolbarItemClick="toolbarItemClick" />
</div>

<div>
	<p> "ToolbarTip5" for dynamic item  leftspace & toggle  & align right</p>
  <ToolbarTip5 :toolbar_define="toolbar_define"  @toolbarItemClick="toolbarItemClick" />
</div>

<div>
	<p> "ToolbarTip6" hundler update</p>
  <ToolbarTip6 :toolbar_define="toolbar_define"  :handler_define="handler_define" 
		                                 @toolbarItemClick="toolbarItemClick"  
                                                 @clickA="clickA"
                                                 @clickB="clickB"
		                                 @toolbarItemToggle="toolbarItemToggle"  
						 />
</div>
</template>

<style scoped>
</style>
