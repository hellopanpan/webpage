<template>
	<div class="homeShouye3">
		<p @click="increment">首页3vuex的数据count</p>
		<p @click="increment">点击增加vuex</p>
		<p @click="decrement">点击减少vuex</p>
		<p style="color:blue;font-size:20px">[{{count}}]</p>
	</div>
</template>
<style>
	.homeShouye3{width:100%;height:100%;background:#fff;box-sizing:border-box;padding-top:20px;}
</style>
<script>
    import {mapActions,mapGetters} from "Vuex"

	export default{
		methods:mapActions(['increment',"decrement"]),
 		 computed:mapGetters(['count'])


	}
</script>