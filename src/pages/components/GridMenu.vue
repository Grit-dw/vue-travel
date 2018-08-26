<template>
  <div class="menu">
    <div class="menublock">
      <swiper :options="swiperOption">
        <swiper-slide v-for="(page, index) of pages" :key="index">
          <div class="menu-icon" v-for="item of page" :key="item.id">
            <div class="icon-img">
              <img class="icon-img-content" :src="item.imgUrl" alt="">
            </div>
            <p class="icon-desc">{{item.desc}}</p>
          </div>
        </swiper-slide>
      </swiper>
      <!--<div class="menu-icon">-->
        <!--<div class="icon-img">-->
          <!--<i class="icon-img-content iconfont">&#xe602;</i>-->
        <!--</div>-->
        <!--<p class="icon-desc">泡温泉</p>-->
      <!--</div>-->
      <!--<div class="menu-icon">-->
        <!--<div class="icon-img">-->
          <!--<i class="icon-img-content iconfont">&#xe6b9;</i>-->
        <!--</div>-->
        <!--<p class="icon-desc">动植物园</p>-->
      <!--</div>-->
      <!--<div class="menu-icon">-->
        <!--<div class="icon-img">-->
          <!--<i class="icon-img-content iconfont">&#xe605;</i>-->
        <!--</div>-->
        <!--<p class="icon-desc">一日游</p>-->
      <!--</div>-->
      <!--<div class="menu-icon">-->
        <!--<div class="icon-img">-->
          <!--<i class="icon-img-content iconfont">&#xe658;</i>-->
        <!--</div>-->
        <!--<p class="icon-desc">必游榜单</p>-->
      <!--</div>-->
      <!--<div class="menu-icon">-->
        <!--<div class="icon-img">-->
          <!--<i class="icon-img-content iconfont">&#xe69c;</i>-->
        <!--</div>-->
        <!--<p class="icon-desc">自然风光</p>-->
      <!--</div>-->
      <!--<div class="menu-icon">-->
        <!--<div class="icon-img">-->
          <!--<i class="icon-img-content iconfont">&#xe650;</i>-->
        <!--</div>-->
        <!--<p class="icon-desc">全部</p>-->
      <!--</div>-->
    </div>
  </div>
</template>
<script type="text/ecmascript-6">
  export default {
    name: 'HomeIcons',
    props: {
      list: Array
    },
    data() {
      return {
        swiperOption: {
          autoplay: false
        }
      }
    },
    computed: {
      pages() {
        const pages = []
        this.list.forEach((item, index) => {
          const page = Math.floor(index / 8)
          if (!pages[page]) {
            pages[page] = []
          }
          pages[page].push(item)
        })
        return pages
      }
    }
  }
</script>
<style lang="stylus" scoped>
  @import '~styles/variables.styl'
  @import '~styles/mixins.styl'
  .menu >>> .swiper-container
    height: 0
    padding-bottom: 50%
  .menu
    margin-top: .1rem
    .menublock
      overflow: hidden
      height: 0
      padding-bottom: 50%
      .menu-icon
        position: relative
        overflow: hidden
        float: left
        width: 25%
        height: 0
        padding-bottom: 25%
        .icon-img
          position: absolute
          top: 0
          left: 0
          right: 0
          bottom: .44rem
          box-sizing: border-box
          padding: .1rem
          .icon-img-content
            height: 100%
            display: block
            margin: 0 auto
        .icon-desc
          position: absolute
          left: 0
          right: 0
          bottom: 0
          height: .44rem
          line-height: .44rem
          color: $darkText
          text-align: center
          ellipsis()
</style>
