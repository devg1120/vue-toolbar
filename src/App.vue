<script setup lang="ts">
//import HelloWorld from './components/HelloWorld.vue'
import Toolbar from './components/Toolbar.vue'
import ToolbarTip from './components/ToolbarTip.vue'
import ToolbarTip2 from './components/ToolbarTip2.vue'
import ToolbarTip3 from './components/ToolbarTip3.vue'


import { ArrowUturnRightIcon  } from './components/@heroicons/vue/24/outline'
import { ArrowUturnLeftIcon  } from './components/@heroicons/vue/24/outline'

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

</template>

<style scoped>
</style>
