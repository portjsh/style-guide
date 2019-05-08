<template>
  <v-app>
    <v-toolbar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>Nuskin</span>
        <span class="font-weight-light">style guide</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn flat href="https://github.com/vuetifyjs/vuetify/releases/latest" target="_blank">
        <span class="mr-2">Latest Release</span>
      </v-btn>
    </v-toolbar>

    <v-content>
      <colorCards/>
    </v-content>
  </v-app>
</template>

<script>
import ColorCards from "./components/ColorCards";

export default {
  name: "App",
  components: {
    ColorCards
  },
  data() {
    return {
      //
    };
  }
};
</script>
