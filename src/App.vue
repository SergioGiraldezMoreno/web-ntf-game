<template>
  <div class="container-fluid p-0">
    <div class="row m-0">
      <Navbar class="col-auto" />
      <router-view class="col pt-2 p-0"/>
    </div>
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";

export default {
  name: 'App',
  components: {
    Navbar,
  },
}
</script>

<style scoped>
div {
  font-family: 'Cinzel', serif;
}
</style>