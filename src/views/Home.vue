<template>
  <div class="page">
    <div class="home-header">
      <h1>台球助手</h1>
      <p>专业的台球教学与约球平台</p>
    </div>
    <div class="feature-grid">
      <div v-for="feature in features" :key="feature.title" class="feature-item">
        <i :class="feature.icon"></i>
        <h3>{{ feature.title }}</h3>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const features = [
  { title: '技术教学', icon: 'fas fa-chalkboard-teacher' },
  { title: '约球社交', icon: 'fas fa-users' },
  { title: '场馆预订', icon: 'fas fa-map-marker-alt' },
  { title: '赛事活动', icon: 'fas fa-trophy' }
]
</script>

<style scoped>
.page {
  padding-bottom: 70px;
}

.home-header {
  background: linear-gradient(135deg, var(--neon-purple), var(--neon-pink));
  color: white;
  padding: 20px;
  border-radius: 15px;
  margin-bottom: 20px;
  position: relative;
  overflow: hidden;
}

.home-header::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(45deg, transparent 45%, rgba(255, 255, 255, 0.1) 50%, transparent 55%);
  animation: glitch 3s infinite;
}

@keyframes glitch {
  0% { transform: translateX(-100%); }
  100% { transform: translateX(100%); }
}

.feature-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 15px;
}

.feature-item {
  background: var(--card-bg);
  padding: 15px;
  border-radius: 12px;
  text-align: center;
  border: 1px solid rgba(0, 255, 255, 0.1);
  transition: all 0.3s ease;
  cursor: pointer;
}

.feature-item:hover {
  transform: translateY(-2px);
  box-shadow: 0 0 20px rgba(0, 255, 255, 0.2);
}

.feature-item i {
  font-size: 32px;
  color: var(--neon-blue);
  margin-bottom: 10px;
  text-shadow: 0 0 10px var(--neon-blue);
}

h1 {
  font-size: 24px;
  margin-bottom: 10px;
}

h3 {
  font-size: 16px;
}
</style> 