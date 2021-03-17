<template>
  <div class="container" id="app">
    <div class="row">
      <div class="col">
        <NavComponent/>
      </div>
    </div>
    <div class="row">
      <div class="col">
        <router-view/>
        <!-- placeholder -->
      </div>
    </div>
  </div>
</template>

<script>
import NavComponent from '@/components/NavComponent.vue'
export default {
  name: 'App',
  components:{
    NavComponent
  }
}
</script>

<style>

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
