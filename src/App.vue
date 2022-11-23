<!-- @format -->

<template>
  <Translate />
  <nav>
    <router-link to="/">{{ $t("btn.home") }}</router-link> |
    <router-link :to="{ name: 'About' }">{{ $t("btn.about") }}</router-link>
    <router-link :to="{ name: 'Jobs' }">{{ $t("btn.jobs") }}</router-link>
  </nav>
  <button @click="redirect">{{ $t("btn.redirect") }}</button>
  <button @click="back">{{ $t("btn.goback") }}</button>
  <button @click="forward">{{ $t("btn.forward") }}</button>
  <router-view />
</template>

<script>
import Translate from "./components/Translate.vue";

export default {
  name: "App",
  components: {
    Translate,
  },

  methods: {
    redirect() {
      this.$router.push({ name: "Home" });
    },
    back() {
      this.$router.go(-1);
    },
    forward() {
      this.$router.go(1);
    },
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

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
  padding: 10px;
  border-radius: 10px;
}

nav a.router-link-exact-active {
  color: white;
  background: crimson;
}

button {
  margin: 0 10px;
  padding: 10px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}
</style>
