<template>
  <div>
    <Card 
      class="card"
      title="Why us?" 
      text="Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
    />
  </div>
</template>

<script>
  import Card from './Card'
  export default {
    components: { 
      Card
    }
  }
</script>

<style lang="scss" scoped>
@import '../assets/styles/colors';
.card { 
  border: 3px solid $green;
}
</style>