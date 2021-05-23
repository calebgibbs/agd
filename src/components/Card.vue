<template>
  <div class="card">
    <div class="inner">
      <h3>{{title}}</h3> 
      <p>{{text}}</p>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      title: String, 
      text: String
    }
  }
</script>

<style lang="scss" scoped>
.card { 
  width: 80%; 
  margin: 0 auto; 
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  padding: 2em;
} 
 
p { 
  margin-top: .5em;
}
</style>