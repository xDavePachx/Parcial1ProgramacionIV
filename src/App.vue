<template>
  <div id="app">
    <b-navbar toggleable type="dark" variant="success">
      <b-container>
        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
        <b-navbar-brand href="#">Barra de navegacion</b-navbar-brand>
        <b-colapse id="nav-collapse" is-nav>
          <b-navbar-nav>
            <b-nav-item to="/" exact exact-active-class="active">Home</b-nav-item>
            <b-nav-item to="/about" exact exact-active-class="active">Calculadora</b-nav-item>
          </b-navbar-nav>
        </b-colapse>
      </b-container>
    </b-navbar>
    <center>
      <img
        width="180"
        alt="Logo casa winterfell"
        src="https://vignette.wikia.nocookie.net/gameofthrones/images/8/8a/House-Stark-Main-Shield.PNG/revision/latest?cb=20170101103142"
      />
    </center>
    <calculadora />
    <home/>
  </div>
</template>

<script>
import Calculadora from "./components/Calculadora.vue";
import Home from './components/Home.vue';

export default {
  name: "App",
  components: {
    Calculadora,
    Home,
  },
};
</script>

<style>
body {
  background: #31475e !important;
}
</style>
