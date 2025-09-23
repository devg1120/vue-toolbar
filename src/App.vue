<script setup lang="ts">
//import HelloWorld from './components/HelloWorld.vue'
import Toolbar from './components/Toolbar.vue'
import ToolbarTip from './components/ToolbarTip.vue'
import ToolbarTip2 from './components/ToolbarTip2.vue'
import ToolbarTip3 from './components/ToolbarTip3.vue'
import ToolbarTip4 from './components/ToolbarTip4.vue'


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

   console.log("Click A:", data);
   alert("Click A");
}

function clickB( data ) {

   console.log("Click B:", data);
   alert("Click B");
}

const toolbar_define = [

{ icon : ArrowUturnRightIcon,
  name : "ArrowUturnRightIcon",
  handler : clickA,
  tooltip : "A         OK",
},
{ icon : ArrowUturnLeftIcon,
  name : "ArrowUturnLeftIcon",
  handler : clickB,
  tooltip : "B         OK",
},
{ icon : RectangleGroupIcon,
  name : "RectangleGroupIcon",
  handler : clickB,
  tooltip : "B         OK",
},
{ icon : Square2StackIcon,
  name : "Square2StackIcon",
  handler : clickB,
  tooltip : "B         OK",
},
{ icon : CalendarIcon,
  name : "CalendarIcon",
  leftspace : true,
  handler : clickB,
  tooltip : "B         OK",
},
{ icon : TrashIcon,
  name : "TrashIcon",
  leftspace : false,
  handler : clickB,
  tooltip : "B         OK",
},

];

function toolbarItemClick(data) {
  console.log(" App toolbar click:", data);


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
	<p> "ToolbarTip4" for dynamic item  leftspace</p>
  <ToolbarTip4 :toolbar_define="toolbar_define"  @toolbarItemClick="toolbarItemClick" />
</div>
</template>

<style scoped>
</style>
