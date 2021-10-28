<template>
  <div class="container-fluid p-0">
    <div class="row m-0">
      <Navbar class="col-auto" />
      <router-view class="col p-0 fs-5"/>
      <SocialMediaBar />
    </div>
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import SocialMediaBar from "./components/SocialMediaBar.vue"

export default {
  name: 'App',
  components: {
    Navbar,
    SocialMediaBar,
  },
}
</script>

<style scoped>
div {
  /* font-family: 'Cinzel', serif; */
  font-family: 'MedievalSharp', cursive; /* TODO: REMOVE THE FONT NOT USED */
}
</style>