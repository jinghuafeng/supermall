<template>
  <div id="home">
    <nav-bar class="home-nav"><span slot="center">购物街</span></nav-bar>
    <home-swiper :banner="banner"></home-swiper>
    <recommend-view :recommend="recommend"></recommend-view>
  </div>
 
</template>

<script>
import NavBar from 'components/common/navbar/NavBar'
import HomeSwiper from './clildComps/HomeSwiper'
import RecommendView from './clildComps/RecommendView'
import {getHomeMultidata} from 'network/home'


  export default {
    name: "Home",
    components: {
      NavBar,
     HomeSwiper,
     RecommendView
    },
    data () {
      return {
        banner:[],
        recommend:[]
      }
    },
    created () {
      getHomeMultidata().then(res=>{
        console.log(res.data.banner.list)   
        this.banner=res.data.banner.list
        this.recommend=res.data.recommend.list
      })
    }
  }
</script>

<style scoped>
.home-nav{
  background-color: var(--color-tint);
  color: #fff;
}
</style>
