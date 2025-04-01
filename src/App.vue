<script setup lang="ts">
import BabylonCanvas from "./components/BabylonCanvas.vue"

</script>

<template>
    <h1>110213041 - model display</h1>
    <BabylonCanvas></BabylonCanvas>
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
</style>
