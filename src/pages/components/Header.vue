<template>
    <div class="header">
      <div class="header-left"><i class="iconfont back-icon">&#xe624;</i></div>
      <div class="header-input"><i class="iconfont search-icon">&#xe632;</i>输入关键字</div>
      <div class="header-right">{{this.city}} <i class="iconfont down-arrow">&#xe62d;</i></div>
    </div>
</template>
<script type="text/ecmascript-6">
  export default {
    name: 'HomeHeader',
    props: {
      city: String
    }
  }
</script>
<style lang="stylus" scoped>
  @import "~styles/variables.styl"
  .header
    display: flex
    line-height: .86rem
    background: $bgColor
    color: #fff
    .header-left
      width: .64rem
      float: left
      text-align: center
      .back-icon
        font-size: .4rem
    .header-input
      flex: 1
      background: #fff;
      margin-top: .12rem
      height: .64rem
      line-height: .64rem
      margin-left: .2rem
      border-radius: .1rem
      color: #ccc
      .search-icon
        margin: 0 .1rem
    .header-right
      width: 1.24rem
      float: right
      text-align: center
      .down-arrow
        font-size: .2rem
</style>
