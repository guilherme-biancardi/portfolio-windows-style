<template>
  <main>
    <MainContent></MainContent>
    <TaskBar></TaskBar>
  </main>
</template>

<script setup lang="ts">
import MainContent from './components/MainContent.vue'
import TaskBar from './components/TaskBar.vue';
</script>

<style scoped>
main {
  width: 100%;
  height: 100vh;
  display: grid;
  grid-template-rows: repeat(auto-fill, minmax(0, 100%)) 56px;
  background: url('./assets/wallpaper.jpg') top;
  background-size: cover;
}
</style>
