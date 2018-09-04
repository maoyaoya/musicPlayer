<template>
  <div>
    <home-header></home-header>
    <home-list></home-list>
  </div>
</template>

<script>
import HomeHeader from './components/header'
import HomeList from './components/list'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeList
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
