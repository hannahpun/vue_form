<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style lang="scss">
#app {
  width: 460px;
  padding: 50px 0px;
  margin: 0 auto;
  border-top: 5px solid $mainColor;
  @include mobile{
    width: 100%;
    padding-left: 30px;
    padding-right: 30px;
  }
}
</style>
