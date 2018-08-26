<template>
    <div class="wrapper">
      <swiper :options="swiperOption" v-if="showSwiper">
        <!-- slides -->
        <swiper-slide v-for="item of list" :key="item.id">
          <img class="swiper-img" :src="item.imgUrl" alt="">
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
</template>
<script type="text/ecmascript-6">
  export default {
    name: 'HomeSwiper',
    props: {
      list: Array
    },
    data() {
      return {
        swiperOption: {
          pagination: {
            el: '.swiper-pagination'
          },
          // 轮播循环
          loop: true,
          // 自动播放
          autoplay: true
        }
      }
    },
    computed: {
      showSwiper () {
        return this.list.length
      }
    }
  }

</script>
<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    opacity: 1;
    background: #fff;
  .wrapper
    width: 100%
    height: 0
    overflow: hidden
    padding-bottom: 24.5vw
    background: #ccc
    .swiper-img
      width: 100%
</style>
