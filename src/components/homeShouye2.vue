<template>
	<div class="homeShouye2">
	<p @click="increment" style="color:blue;font-size:20px">[{{count}}]</p>
		<p @click="increment">首页2可点击切换组件</p>
		<component v-bind:is="currentView" >
		</component>
	</div>
	
</template>
<style>
	.homeShouye2{width:100%;height:100%;background:#fff;box-sizing:border-box;padding-top:20px;}
</style>
<script>

import Home2 from "./homeShouye3.vue"
import {mapGetters,mapActions} from 'vuex'
var Home = {
  template: '<p>Welcome home!</p>'
};
export default{
	data(){
		return {
			"currentView": "Home"
		}

	},
	components:{
		Home,
		Home2
	},
	methods:mapActions(['increment']),
	computed:mapGetters(['count'])
}


</script>