<template>
  <div class="d-flex flex-row first">
    <!-- Side bar -->
    <v-card tile width="15%" class="mx-auto">
      <v-navigation-drawer permanent color="black">
        <v-btn class="black my-5 px-2">
          <v-img
            max-height="100"
            max-width="150"
            src="../img/Icon.png"
            class="ma-2"
          ></v-img>
        </v-btn>

        <v-list dense nav class=" px-2">
          <v-list-item v-for="item in items" :key="item.title" link>
            <v-list-item-icon>
              <v-icon color="white">{{ item.icon }}</v-icon>
            </v-list-item-icon>

            <v-list-item-content>
              <v-list-item-title class="white--text">{{
                item.title
              }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>

        <v-sheet color="black white--text" width="85%" class="mt-5 mx-5">
          <p class="text-uppercase">Playlists</p>
          <!-- <v-text >Playlists</v-text> -->
        </v-sheet>
      </v-navigation-drawer>
    </v-card>
    <!-- navbar -->
    <v-card width="85%" style="border-radius:0">
      <v-app-bar color="grey darken-4 accent-4" flat dense dark>
        <v-div>
          <v-btn x-small fab class="mr-2 black">
            <v-icon>chevron_left</v-icon>
          </v-btn>
          <v-btn x-small fab class="black">
            <v-icon>chevron_right</v-icon>
          </v-btn>
        </v-div>
        <v-spacer></v-spacer>

        <v-div class="relative ">
          <v-div class="d-flex flex-row align-center ">
            <v-btn
              @click="showDrop = !showDrop"
              class="transparent"
              height="35"
              depressed
              rounded
            >
              <img
                height="40"
                width="40"
                style="border-radius:50%"
                src="https://cdn.vuetifyjs.com/images/john.jpg"
                alt="John"
              />
              <p class="mb-0">John vanbasken</p>
              <v-icon>
                {{ showDrop === true ? "arrow_drop_down" : "arrow_drop_up" }}
              </v-icon>
              <!-- <v-icon>arrow_drop_up</v-icon> -->
            </v-btn>
          </v-div>
          <v-div
            v-if="showDrop === true"
            style="margin-bottom:-72px"
            class="absolute d-flex flex-column"
          >
            <v-btn
              tile
              style="border-bottom:1px solid white"
              @click="showDrop = !showDrop"
            >
              Account
            </v-btn>
            <v-btn tile @click="showDrop = !showDrop">Logout</v-btn>
          </v-div>
        </v-div>
      </v-app-bar>

      <div class="main red darken-4">
        <!-- <v-card color="pink" style="border-radius:0"></v-card> -->
      </div>
    </v-card>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showDrop: false,
      items: [
        { title: "Home", icon: "home" },
        { title: "Search", icon: "search" },
        { title: "Your Library", icon: "equalizer" },
      ],
      right: null,
    };
  },

  //   methods: {
  //      const _getGenres= async(token) =>{
  // const result=await fetch("https://api.spotify.com/v1/audio-analysis/6EJiVf7U0p1BBfs0qqeb1f", {
  //   method: "GET",
  //   headers: {
  //     Authorization: `Bearer ${userAccessToken}`
  //   }
  // })
  // .then(response => response.json())
  // .then(({beats}) => {
  //   beats.forEach((beat, index) => {
  //     console.log(`Beat ${index} starts at ${beat.start}`);
  //   })
  // })
  //     }
  //   },
};
</script>

<style lang="scss" scoped>
.first {
  overflow: hidden;
  height: 100vh;
  width: 100%;
}

.main {
  height: 100%;
  width: 100%;
}
</style>
