<template>
  <v-app>
    <v-main>
      <Nav />
      <Carousel />
      <Bandas />
      <Contacto />
      <Footer />
    </v-main>
  </v-app>
  
</template>

<script>
import Nav from "./components/Nav.vue";
import Carousel from "./components/Carousel";
import Bandas from "./components/Bandas.vue";
import Contacto from "./components/Contacto.vue";
import Footer from "./components/Footer.vue";


export default {
  name: "App",

  components: {
    Nav,
    Carousel,
    Bandas,
    Contacto,
    Footer,
  },

  data: () => ({
    //
  }),
};
</script>
<style>


</style>