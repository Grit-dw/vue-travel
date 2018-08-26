<template>
    <div>
      <home-header :city="city"></home-header>
      <home-swiper :list="swiperList"></home-swiper>
      <home-menu :list="menuList"></home-menu>
      <home-recommend :list="recommendList"></home-recommend>
      <home-weeked :list="weekendList"></home-weeked>
    </div>
</template>
<script type="text/ecmascript-6">
  import HomeHeader from './components/Header.vue'
  import HomeSwiper from './components/Swiper.vue'
  import HomeMenu from './components/GridMenu.vue'
  import HomeRecommend from './components/Recommend.vue'
  import HomeWeeked from './components/Weekend.vue'
  import axios from 'axios'
  export default {
    data () {
      return {
        city: '',
        swiperList: [],
        menuList: [],
        recommendList: [],
        weekendList: []
      }
    },
    methods: {
      getHomeInfo() {
        axios.get('/api/index.json').then(this.getHomeInfoSucc)
      },
      getHomeInfoSucc(res) {
        res = res.data
        if (res.ret && res.data) {
          this.city = res.data.city
          this.swiperList = res.data.swiperList
          this.menuList = res.data.iconList
          this.recommendList = res.data.recommendList
          this.weekendList = res.data.weekendList
        }
        console.log(res)
      }
    },
    mounted() {
      this.getHomeInfo()
    },
    components: {
      HomeHeader,
      HomeSwiper,
      HomeMenu,
      HomeRecommend,
      HomeWeeked
    }
  }
</script>
<style></style>
