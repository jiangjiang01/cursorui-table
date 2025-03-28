<template>
  <div class="page">
    <h2 class="page-title">个人中心</h2>
    <div class="profile-header">
      <div class="profile-avatar"></div>
      <h2>{{ userInfo.username }}</h2>
      <p>{{ userInfo.bio }}</p>
      <div class="stats">
        <div class="stat-item">
          <span class="number">{{ userInfo.posts }}</span>
          <span class="label">动态</span>
        </div>
        <div class="stat-item">
          <span class="number">{{ userInfo.followers }}</span>
          <span class="label">粉丝</span>
        </div>
        <div class="stat-item">
          <span class="number">{{ userInfo.following }}</span>
          <span class="label">关注</span>
        </div>
      </div>
    </div>
    <div class="menu-list">
      <div v-for="item in menuItems" :key="item.id" class="menu-item" @click="handleMenuClick(item)">
        <i :class="item.icon"></i>
        <span>{{ item.title }}</span>
        <i class="fas fa-chevron-right arrow"></i>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
interface MenuItem {
  id: number
  title: string
  icon: string
  action: string
}

interface UserInfo {
  username: string
  bio: string
  posts: number
  followers: number
  following: number
}

const userInfo: UserInfo = {
  username: '台球爱好者',
  bio: '热爱台球运动，追求技术进步',
  posts: 15,
  followers: 128,
  following: 56
}

const menuItems: MenuItem[] = [
  { id: 1, title: '学习记录', icon: 'fas fa-history', action: 'learning-history' },
  { id: 2, title: '我的预约', icon: 'fas fa-calendar', action: 'appointments' },
  { id: 3, title: '收藏夹', icon: 'fas fa-bookmark', action: 'favorites' },
  { id: 4, title: '设置', icon: 'fas fa-cog', action: 'settings' }
]

const handleMenuClick = (item: MenuItem) => {
  console.log('点击菜单项:', item.action)
  // TODO: 实现菜单项功能
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

.profile-header {
  text-align: center;
  margin-bottom: 30px;
  padding: 20px;
  background: var(--card-bg);
  border-radius: 15px;
  border: 1px solid rgba(0, 255, 255, 0.1);
  position: relative;
  overflow: hidden;
}

.profile-header::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(45deg, transparent 45%, rgba(0, 255, 255, 0.1) 50%, transparent 55%);
  animation: glitch 3s infinite;
}

@keyframes glitch {
  0% { transform: translateX(-100%); }
  100% { transform: translateX(100%); }
}

.profile-avatar {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  background: linear-gradient(45deg, var(--neon-pink), var(--neon-purple));
  margin: 0 auto 15px;
  border: 3px solid var(--neon-blue);
  box-shadow: 0 0 20px var(--neon-blue);
}

.profile-header h2 {
  font-size: 20px;
  margin-bottom: 5px;
  color: var(--neon-blue);
  text-shadow: 0 0 10px var(--neon-blue);
}

.profile-header p {
  color: rgba(255, 255, 255, 0.6);
  margin-bottom: 20px;
}

.stats {
  display: flex;
  justify-content: space-around;
  margin-top: 20px;
  position: relative;
  z-index: 1;
}

.stat-item {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.stat-item .number {
  font-size: 20px;
  font-weight: bold;
  color: var(--neon-pink);
  text-shadow: 0 0 10px var(--neon-pink);
}

.stat-item .label {
  font-size: 12px;
  color: rgba(255, 255, 255, 0.6);
  margin-top: 5px;
}

.menu-list {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.menu-item {
  display: flex;
  align-items: center;
  padding: 15px;
  background: var(--card-bg);
  border-radius: 10px;
  gap: 10px;
  border: 1px solid rgba(0, 255, 255, 0.1);
  transition: all 0.3s ease;
  cursor: pointer;
}

.menu-item:hover {
  transform: translateX(5px);
  border-color: var(--neon-blue);
  box-shadow: 0 0 15px rgba(0, 255, 255, 0.2);
}

.menu-item i {
  color: var(--neon-blue);
  text-shadow: 0 0 10px var(--neon-blue);
}

.menu-item span {
  flex: 1;
}

.menu-item .arrow {
  font-size: 12px;
  color: rgba(255, 255, 255, 0.3);
  transition: all 0.3s ease;
}

.menu-item:hover .arrow {
  color: var(--neon-blue);
  transform: translateX(5px);
}
</style> 