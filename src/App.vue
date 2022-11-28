<template>
  <div id="app">

    <HeaderComp/>
    <MainComp/>

  </div>
</template>

<script>
import MainComp from './components/MainComp.vue'
import HeaderComp from './components/HeaderComp.vue'

export default {
  name: 'App',
  components: {

    MainComp,
    HeaderComp,
  },
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  height: 100vh;
 
}
</style>
