<template>
  <v-app>
    <Header></Header>
    <v-main>
      <v-container>
        <router-view></router-view>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import Header from './components/Header/Header.vue'
export default {
  name: 'App',
  data: () => ({
  }),
  components: {
    Header
  }
};
</script>
