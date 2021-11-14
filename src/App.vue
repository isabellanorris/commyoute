<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/calculator">Calculator</router-link> |
      <router-link to="/volunteer">Volunteer</router-link> |
      <router-link to="/sessions">Join In</router-link> |
      <router-link to="/charities">Charities</router-link>
    </div>
    <router-view />
    <Footer />
  </div>
</template>

<script>
  import Footer from "@/components/Footer.vue";
  export default {
    name: "App",
    components: {
      Footer,
    },
  };
</script>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Oswald:wght@200;400&display=swap");

  #app {
    font-family: "Oswald", sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #ffffff;
    background-color: #1f7087;
  }

  #nav {
    padding: 30px;
  }

  #nav a {
    font-weight: bold;
    color: #ffffff;
  }

  #nav a.router-link-exact-active {
    color: #4ea3bb;
  }
</style>
