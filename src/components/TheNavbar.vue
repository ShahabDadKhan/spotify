<template>
  <div class="d-flex flex-row">
    <!-- Side bar -->
    <v-card height="95vh" tile width="15%" class="mx-auto">
      <v-navigation-drawer permanent color="black" class="">
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
      </v-navigation-drawer>
    </v-card>
    <!-- navbar -->
    <v-app-bar width="85%" color="grey darken-4 accent-4" dense dark>
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
};
</script>

<style lang="sass" scoped>
// .v-btn--active.no-active::before {
//   opacity: 0 !important;
// }
</style>
