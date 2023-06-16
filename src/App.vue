<script setup>
import { useColorMode } from "@vueuse/core";
import HelloWorld from "./components/HelloWorld.vue";
import IconMoon from "./components/iconMoon.vue";
import IconSun from "./components/IconSun.vue";
const colorMode = useColorMode();
const switchTheme = () => {
  colorMode.value = colorMode.value === "dark" ? "light" : "dark";
};
</script>

<template>
  <header style="display: flex; justify-content: space-between; height: 50px; align-items: center">
    <h1 style="font-size:1.2rem">Build with Ben #23</h1>

    <button
      @click="switchTheme"
      style="display: flex; align-items: center"
    >
      <IconSun v-if="colorMode==='light'" />
      <IconMoon v-if="colorMode==='dark'" />
    </button>
  </header>
  <h1>{{ colorMode }}</h1>
  <a
    href="https://vuejs.org/"
    target="_blank"
  >
    <img
      src="./assets/vue.svg"
      class="logo vue"
      alt="Vue logo"
    />
  </a>

  <HelloWorld msg="Vite + Vue" />
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}

.dark {
  background-color: #222;
  color: #fff;
}
</style>
