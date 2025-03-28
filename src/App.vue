<script setup lang="ts">
import TabBar from './components/TabBar.vue'
</script>

<template>
  <div class="app">
    <router-view></router-view>
    <TabBar />
  </div>
</template>

<style>
@import './assets/main.css';

.app {
  min-height: 100vh;
  background-color: var(--dark-bg);
}
</style>
