<template>
  <v-app>
    <!-- <the-navbar /> -->
    <router-view></router-view>
  </v-app>
</template>

<script>
// import HelloWorld from './components/HelloWorld';
// import TheNavbar from "./components/TheNavbar.vue";

export default {
  name: "App",

  components: {
    // HelloWorld
    // TheNavbar,
  },

  data: () => ({
    //
  }),
};
</script>

// fetch("https://api.spotify.com/v1/audio-analysis/6EJiVf7U0p1BBfs0qqeb1f", {
// method: "GET", // headers: { // Authorization: `Bearer ${userAccessToken}` //
} // }) // .then(response => response.json()) // .then(({beats}) => { //
beats.forEach((beat, index) => { // console.log(`Beat ${index} starts at
${beat.start}`); // }) // })
