<template>
  <nav class="nav-bar">
    <router-link
      v-for="item in navItems"
      :key="item.path"
      :to="item.path"
      class="nav-item"
      :class="{ active: currentRoute === item.path }"
    >
      <i :class="item.icon"></i>
      <span>{{ item.text }}</span>
    </router-link>
  </nav>
</template>

<script setup lang="ts">
import { computed } from 'vue'
import { useRoute } from 'vue-router'

const route = useRoute()
const currentRoute = computed(() => route.path)

const navItems = [
  { path: '/home', icon: 'fas fa-home', text: '首页' },
  { path: '/learn', icon: 'fas fa-graduation-cap', text: '学习' },
  { path: '/social', icon: 'fas fa-users', text: '社交' },
  { path: '/profile', icon: 'fas fa-user', text: '我的' }
]
</script>

<style scoped>
.nav-bar {
  position: fixed;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 100%;
  max-width: 375px;
  background-color: rgba(26, 26, 46, 0.9);
  padding: 10px;
  border-radius: 10px;
  display: flex;
  justify-content: space-around;
  margin-top: 10px;
  border: 1px solid rgba(0, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  z-index: 1000;
}

.nav-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-decoration: none;
  color: rgba(255, 255, 255, 0.6);
  transition: all 0.3s ease;
}

.nav-item.active {
  color: var(--neon-blue);
  text-shadow: 0 0 10px var(--neon-blue);
}

.nav-item i {
  font-size: 24px;
  margin-bottom: 4px;
}

.nav-item span {
  font-size: 12px;
}
</style> 