<template>
  <v-app>
    <AppBar />
    <v-main>
      <DateTime />
    </v-main>
  </v-app>
</template>

<script>
import AppBar from './components/AppBar';
import DateTime from './components/DateTime';

export default {
  name: 'App',

  components: {
    AppBar,
    DateTime,
  },

  data: () => ({
    //
  }),
};
</script>

<style>
@font-face {
  font-family: "Product Sans Regular";
  src: local("Product Sans Regular"),
    url(./fonts/Product-Sans-Regular.ttf) format("truetype");
}

html {
  overflow-y: auto;
}
</style>