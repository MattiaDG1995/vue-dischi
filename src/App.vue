<template>
  <div id="app" class="bg-dark">
    <HeaderComp />
    <MainComp />
  </div>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue' 


export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp,
  },
  data(){
    return{
      

    }
  },
  
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

#app{
  height: 100vh;
}





</style>
