<template>
    <div class="wrapper">
      <swiper :options="swiperOption">
        <!-- slides -->
        <swiper-slide v-for="item of swiperList" :key="item.id">
          <img class="swiper-img" :src="item.imgUrl" alt="">
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
</template>
<script type="text/ecmascript-6">
  export default {
    name: 'HomeSwiper',
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
        },
        swiperList: [
          {
          id: '0001',
          imgUrl: 'https://source.qunarzz.com/site/images/wap/home/recommend/iphoneplus/anquan_20180716.png'
        },
          {
          id: '0002',
          imgUrl: 'https://source.qunarzz.com/site/images/wap/home/recommend/iphoneplus/dujia_shuqi_banner_20180710.jpg'
        }
        ]
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
