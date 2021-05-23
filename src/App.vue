<template>
  <div class="app"> 
    <Navigation/>
    <router-view/>  
    Hello
  </div>
</template>

<script> 
import Navigation from './components/Navigation'
  export default {
    components: {
      Navigation
    }
  }
</script>

<style lang="scss" scoped>

</style>