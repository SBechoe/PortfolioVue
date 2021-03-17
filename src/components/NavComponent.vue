<template>
  <div id="nav">
    <router-link to="/" exact>Home</router-link> |
    <router-link to="/aboutMe" exact>About Me</router-link> |
    <router-link to="/contact" exact>Contact</router-link>
  </div>
</template>

<script>
export default {
  name: 'NavComponent'
}
</script>

<style lang="css" scoped>
</style>
