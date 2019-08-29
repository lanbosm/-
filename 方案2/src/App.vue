<template>
  <div id="app">
   

    <VueDragResize :w="200" :h="200" v-on:resizing="resize" v-on:dragging="resize">
　　

　　<div class="box" :style="{width: + vw+ 'px',height:+vh+'px'}">
　
　　　　  <img alt="Vue logo" src="./assets/logo.png">
　　</div>
</VueDragResize>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import VueDragResize from 'vue-drag-resize' //缩放、拖拽
export default {
  name: 'app',
 components: {
　　VueDragResize
},

data() {
　　return {
　　　　vw: 0,
　　　　vh: 0,
　　　　top: 0,
　　　　left:0
　　};
},
created() {
　　this.vw = 200 + "px";
　　this.vh = 200 + "px";
},
methods:{
	
resize(newRect) {
this.vw = newRect.width;
this.vh = newRect.height;
this.top = newRect.top;
this.left = newRect.left;
}
}
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

img{
	width:100%;
	height:100%;
}
</style>
