<template>
    <div class="search">
      <input type="text" class="search-input" placeholder="输入城市名或拼音">
    </div>
</template>
<script type="text/ecmascript-6">
  export default {
    name: 'CitySearch'
  }
</script>
<style lang="stylus" scoped>
  @import '~styles/variables.styl'
  .search
    height: .72rem
    background: $bgColor
    padding: 0 .1rem
    .search-input
      height: .62rem
      width: 100%
      box-sizing: border-box
      padding: 0 .1rem
      line-height: .62rem
      text-align: center
      border-radius: .06rem
      color: #666
</style>
