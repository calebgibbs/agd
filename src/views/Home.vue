<template>
  <div>
    <HeroImage/>  
    <Services/> 
    <div class="cards">
      <About/>
      <Why/>
    </div> 
    <Contact/>
  </div>
</template>

<script>
  import HeroImage from '../components/HeroImage' 
  import Services from '../components/HomeServices' 
  import About from '../components/AboutUs'
  import Why from '../components/WhyUs'
  import Contact from '../components/ContactForm'
  export default {
    components: {
      HeroImage, 
      Services, 
      About, 
      Why, 
      Contact
    }
  }
</script>

<style lang="scss" scoped> 
@import '../assets/styles/mediaqueries';
.cards { 
  display: grid; 
  grid-template-columns: repeat(2, 1fr); 
  margin-top: 6em;
  margin-bottom: 6em;
} 

@include mobile-landscape {
  .cards { 
    grid-template-columns: repeat(1, 1fr);
    grid-gap: 2em;
  }
} 

@include mobile-portait {
  .cards { 
    grid-template-columns: repeat(1, 1fr); 
    grid-gap: 2em;
  }
}

</style>