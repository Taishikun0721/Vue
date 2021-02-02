<template>
  <v-card
    color="grey lighten-4"
    flat
    height="80px"
    tile
  >
    <v-toolbar dense>
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <router-link to="/"><v-toolbar-title>Vue Sample Application</v-toolbar-title></router-link>

      <v-spacer></v-spacer>

    <router-link to="/typing">
      <v-btn icon>
        <v-icon  @click="switchInput">mdi-magnify</v-icon>
      </v-btn>
    </router-link>

    <router-link to="profile">
      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>
    </router-link>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-toolbar>
  </v-card>
</template>

<script>
export default {
  data() {
    return {
      showInput: false
    }
  },
  methods: {
    switchInput() {
      this.showInput = !this.showInput
    }
  }
}
</script>

<style scoped>
li a {
  text-decoration: none;
}
</style>
