<template>
  <div id="app">
  
    <transition name="fade"><router-view :totle="totle"></router-view></transition>
    <div class="footer navbar">
		<ul class="nav navbar-nav">
			<li class="active"><router-link  to='/home'><span class="glyphicon glyphicon-home"></span> 首页</router-link></li>
			 <li><router-link  to='/name'><span class="glyphicon glyphicon-list"></span>内容区</router-link></li>
			<li><router-link  to='/person'><span class="glyphicon glyphicon-fire"></span> 个人中心</router-link></li>
		 </ul>
  	</div>
 </div>
</template>

<script>
import Navview from './components/nav.vue'
import ContentView from './components/content.vue'  
import FllowView from './components/fllowView.vue' 
import {mapGetters,mapActions} from 'vuex'

export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      showif:true,
      totle:"App.vue上的数据",
    }
  },
  components:{ 
      Navview,
      ContentView,
      FllowView,
      
  },
  methods:mapActions(['increment',"decrement"]),
  computed:mapGetters(['count']),
  mounted(){
    
  }

}
</script>

<style>
.footer{
  width:100%;height:10%;position:absolute;bottom:0px;background:#333
}
.footer ul{width:100%;height:100%;margin:0;padding:0;}
.footer li{ width:33%;height:10%;float:left;}
html,body{
  height:100%;
  width:100%;
}
#logo{position:absolute;top:0;left:0.5rem;width:50px;height:50px;z-index:2}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  height:100%;
  width:100%;
}
.slide-fade-enter-active {
  transition: all .3s ease;
}
.slide-fade-leave-active {
  transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.slide-fade-enter, .slide-fade-leave-active {
  transform: translateX(10px);
  opacity: 0;
}
h1, h2 {
  font-weight: normal;
}
div,p,h1,h2,h3,a{margin:0;padding:0}
ul {
  list-style-type: none;
  padding: 0;
}
.fade-enter-active, .fade-leave-active {
    transition: opacity .5s
  }
  .fade-enter, .fade-leave-to /* .fade-leave-active in <2.1.8 */ {
    opacity: 0
  }

</style>
