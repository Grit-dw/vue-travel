<template>
    <div>
      <home-header></home-header>
      <router-view></router-view>
    </div>
</template>
<script type="text/ecmascript-6">
  import HomeHeader from './components/Header.vue'
  export default {
    components: {
      HomeHeader
    }
  }
</script>
<style></style>
