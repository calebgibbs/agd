<template>
  <div>
    <HeroImage/>  
    <Services/>
  </div>
</template>

<script>
  import HeroImage from '../components/HeroImage' 
  import Services from '../components/HomeServices'
  export default {
    components: {
      HeroImage, 
      Services
    }
  }
</script>

<style lang="scss" scoped>

</style>