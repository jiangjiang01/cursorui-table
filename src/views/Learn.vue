<template>
  <div class="page">
    <h2 class="page-title">学习</h2>
    <div class="video-list">
      <div v-for="video in videos" :key="video.id" class="video-item" @click="playVideo(video)">
        <div class="video-thumbnail">
          <i class="fas fa-play"></i>
        </div>
        <div class="video-info">
          <h3>{{ video.title }}</h3>
          <p>{{ video.description }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
interface Video {
  id: number
  title: string
  description: string
  url: string
}

const videos: Video[] = [
  {
    id: 1,
    title: '台球基础入门教程',
    description: '学习正确的握杆姿势和基本打法',
    url: '#'
  },
  {
    id: 2,
    title: '进阶技巧讲解',
    description: '高阶技巧和战术分析',
    url: '#'
  },
  {
    id: 3,
    title: '比赛实战技巧',
    description: '职业选手比赛技巧分析',
    url: '#'
  }
]

const playVideo = (video: Video) => {
  console.log('播放视频:', video.title)
  // TODO: 实现视频播放功能
}
</script>

<style scoped>
.page {
  padding-bottom: 70px;
}

.page-title {
  font-size: 18px;
  margin-bottom: 20px;
  color: var(--neon-blue);
  border-bottom: 2px solid var(--neon-blue);
  padding-bottom: 10px;
  text-transform: uppercase;
  letter-spacing: 2px;
  text-shadow: 0 0 10px var(--neon-blue);
}

.video-list {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.video-item {
  display: flex;
  gap: 15px;
  padding: 15px;
  background: var(--card-bg);
  border-radius: 10px;
  border: 1px solid rgba(0, 255, 255, 0.1);
  cursor: pointer;
  transition: all 0.3s ease;
}

.video-item:hover {
  transform: translateX(5px);
  border-color: var(--neon-blue);
}

.video-thumbnail {
  width: 120px;
  height: 80px;
  background: rgba(0, 255, 255, 0.1);
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden;
}

.video-thumbnail i {
  color: var(--neon-pink);
  text-shadow: 0 0 10px var(--neon-pink);
  font-size: 24px;
}

.video-info h3 {
  font-size: 16px;
  margin-bottom: 5px;
  color: var(--neon-blue);
}

.video-info p {
  font-size: 14px;
  color: rgba(255, 255, 255, 0.6);
}
</style> 