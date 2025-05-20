<template>
  <!-- <ContadorView></ContadorView> -->
  <!-- <EstudianteTablaViewV /> -->
  <BecarioView />
</template>

<script>
//import EstudianteTablaViewV from "@/views/EstudianteTablaViewV.vue";
//import ContadorView from "@/views/ContadorView.vue";
import BecarioView from "@/views/BecarioView.vue";

export default {
  name: "App",
  components: {
    //ContadorView,
    //EstudianteTablaViewV,
    BecarioView,
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
  margin-top: 60px;
}
</style>
