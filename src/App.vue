<template>
  <Header />
  <Gallery />
  <Footer />
</template>

<script>
import Header from "./components/Header.vue";
import Gallery from "./components/Gallery.vue";
import Footer from "./components/Footer.vue";
import "./assets/css/global.css";

export default {
  name: "App",
  components: {
    Header,
    Gallery,
    Footer,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
