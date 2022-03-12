<script setup>
import Anatomy from "./components/Anatomy.vue";
</script>

<template>
  <h1>CSS SELECTOR ANATOMY</h1>
  <Anatomy />
</template>

<style>
* {
  box-sizing: border-box;
}
body {
  background-color: #333;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  margin: 0;
  display: grid;
  place-content: center;
  font-size: 2.5vw;
  user-select: none;
}
h1 {
  text-align: center;
  color: #ddd;
  text-shadow: #ccc 1.5px 0 3px;
}
</style>