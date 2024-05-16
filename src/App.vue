<template>
  <div id="app">
    <main class="container">
      <h1 class="py-2 text-center fw-bold">Cuestionario Curso</h1>
      <hr>
      <formInteractivo />
    </main>
  </div>
</template>

<script>
import formInteractivo from "./components/formInteractivo.vue";
export default {
  name: "App",
  components: {
    formInteractivo,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center;
  color: #2c3e50;
  margin-top: 60px; */
}
</style>
