
<template>
  <div class="galeria pa-16 ma-16">
    <h1 class="letter mb-16">¡Escuchá tus canciones favoritas!</h1>

    <div class="container">
      <v-carousel>
        <v-carousel-item
          v-for="(item, i) in items"
          :key="i"
          :src="item.src"
          reverse-transition="fade-transition"
          transition="fade-transition"
        > <h3 class="genero">{{item.genero}}</h3>
        </v-carousel-item>
      </v-carousel>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          src: require("../assets/rock.jpg"), genero:'Rock'
        },
        {
          src: require("../assets/damas.jpg"), genero:'Cumbia'
        },
        {
          src: require("../assets/reggae.jpg"),genero:'Reggae'
        },
        {
          src: require("../assets/varias.jpg"),genero:'y mucho más...'
        },
      ],
      
    };
  },
};
</script>
<style>
.letter {
  text-align: center;
  color: grey;
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
}
.genero{
  font-size: 150px;
      font-family: 'Open Sans', sans-serif;
  color: #0514579f;
    font-family: 'Permanent Marker', cursive;
}
</style>
