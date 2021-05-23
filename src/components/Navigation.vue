<template>
  <div class="nav">
    <div class="logo">
      <router-link to="/">
        <img src="../assets/images/logos/logo.png" alt="logo" width="75px">
      </router-link>
    </div> 
    <div class="links">
      <ul>
        <li><router-link to="/">Home</router-link></li>
        <li><router-link to="/services">Services</router-link></li>
        <li><router-link to="/photos">Photos</router-link></li>
        <li><router-link to="/contact">Contact</router-link></li>
      </ul>
    </div>
  </div>
</template>

<script>
  export default {
    
  }
</script>

<style lang="scss" scoped> 
@import '../assets/styles/colors';
.nav {
  padding: .5em; 
  display: flex;  
  justify-content: space-between;
  align-items: center; 
  border-bottom: 3px solid $yellow;
} 

ul { 
 padding: 0; 
 margin: 0; 
} 

li {
  display: inline-block; 
  list-style-type: none; 
  font-size: 1.3em; 
  margin: 0 .7em;
} 

a { 
  text-decoration: none; 
  color: inherit;  
  transition: color .1s ease-in-out;
  &:hover {
    color: $yellow;
  }
}
</style>