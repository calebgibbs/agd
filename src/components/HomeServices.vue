<template>
  <div class="services">
    <div class="service">
      <img src="../assets/images/home/interior.jpg" alt=""> 
      <h3>Interior</h3>
    </div>
    <div class="service">
      <img src="../assets/images/home/exterior.jpg" alt=""> 
      <h3>Exterior</h3>
    </div>
    <div class="service">
      <img src="../assets/images/home/commercial.jpg" alt=""> 
      <h3>Commercial</h3>
    </div>
  </div>
</template>

<style lang="scss" scoped> 
@import '../assets/styles/mediaqueries';
.services { 
  display: grid; 
  grid-template-columns: repeat(3, 1fr); 
  div { 
    text-align: center;
  }
} 

img { 
  border-radius: 50%; 
  border: 3px solid #fff; 
  margin-top: -23%;
} 

h3 { 
  font-size: 1.5em; 
  margin-top: .5em; 
  font-weight: lighter;
}  

@mixin mobile {
  img { 
    width: 70%; 
    margin-top: 0; 
    border-radius: 0;
  } 
  h3 { 
    font-size: 1em;
  }
}

@include mobile-landscape{ 
  @include mobile();
} 

@include mobile-portait{ 
  @include mobile();
}
</style>