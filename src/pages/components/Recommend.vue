<template>
    <div>
      <div class="title">热销推荐</div>
      <ul>
        <li class="item border" v-for="item of list" :key="item.id">
          <div class="item-img-wrapper" >
            <img class="item-img" :src="item.imgUrl" alt="">
          </div>
          <div class="item-info">
            <p class="item-title">{{item.title}}</p>
            <p class="item-desc">{{item.desc}}</p>
            <button class="item-button">查看详情</button>
          </div>
        </li>
      </ul>
    </div>
</template>
<script type="text/ecmascript-6">
  export default {
    name: 'HomeRecommend',
    props: {
      list: Array
    },
    data () {
      return {}
    }
  }
</script>
<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
    background: #eee
    text-indent: .2rem
    line-height: .8rem
    margin-top: .2rem
  .item
    display: flex
    height: 1.9rem
    overflow: hidden
    .item-img
      width: 1.7rem
      height: 1.7rem
      padding: .1rem
    .item-info
      padding: .1rem
      flex: 1
      min-width: 0
      .item-title
        line-height: .54rem
        font-size: .32rem
        ellipsis()
      .item-desc
        line-height: .4rem
        color: #ccc
        font-size: .25rem
        ellipsis()
      .item-button
        background: #ff9300
        padding: 0 .2rem
        border-radius: .06rem
        margin-top: .2rem
        color: #fff
        line-height: .44rem
</style>
