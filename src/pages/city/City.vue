<template>
    <div>
      <city-header></city-header>
      <city-search></city-search>
    </div>
</template>
<script type="text/ecmascript-6">
  import CityHeader from './components/CityHeader'
  import CitySearch from './components/Search'
  export default {
    name: 'City',
    components: {
      CityHeader,
      CitySearch
    }
  }
</script>
<style lang="stylus" scoped></style>
