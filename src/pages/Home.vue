<template>
    <div>
      <home-header :city="defaultCity"></home-header>
      <home-swiper :list="swiperList"></home-swiper>
      <home-menu :list="menuList"></home-menu>
      <home-recommend :list="recommendList"></home-recommend>
      <home-weekend :list="weekendList"></home-weekend>
    </div>
</template>
<script type="text/ecmascript-6">
  import HomeHeader from './components/Header.vue'
  import HomeSwiper from './components/Swiper.vue'
  import HomeMenu from './components/GridMenu.vue'
  import HomeRecommend from './components/Recommend.vue'
  import HomeWeekend from './components/Weekend.vue'
  import axios from 'axios'
  export default {
    data () {
      return {
        defaultCity: '',
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
      getHomeCityInfo() {
        axios.get('/api/city.json').then(this.getCitySucc)
      },
      getHomeInfoSucc(res) {
        res = res.data
        if (res.ret && res.data) {
          this.swiperList = res.data.swiperList
          this.menuList = res.data.iconList
          this.recommendList = res.data.recommendList
          this.weekendList = res.data.weekendList
        }
      },
      getCitySucc(res) {
        res = res.data
        if (res.ret && res.data) {
          this.defaultCity = res.data.hotCities[2].name
        }
      }
    },
    mounted() {
      this.getHomeInfo()
      this.getHomeCityInfo()
    },
    components: {
      HomeHeader,
      HomeSwiper,
      HomeMenu,
      HomeRecommend,
      HomeWeekend
    }
  }
</script>
<style></style>
