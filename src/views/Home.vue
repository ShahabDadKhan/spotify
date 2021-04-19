<template>
  <v-app>
    <the-navbar />
  </v-app>
</template>

<script>
import TheNavbar from "../components/TheNavbar.vue";
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: "Home",
  components: {
    TheNavbar,
    // HelloWorld
  },
};
</script>
