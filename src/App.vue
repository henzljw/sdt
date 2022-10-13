<template>
  <v-app>
    <AppBar />
    <v-main>
      <DateTime />
    </v-main>
    <FooterBar />
  </v-app>
</template>

<script>
import AppBar from './components/AppBar';
import DateTime from './components/DateTime';
import FooterBar from './components/FooterBar';

export default {
  name: 'App',

  components: {
    AppBar,
    DateTime,
    FooterBar
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