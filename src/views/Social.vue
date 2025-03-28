<template>
  <div class="page">
    <h2 class="page-title">社交</h2>
    <div class="action-bar">
      <button class="post-btn" @click="showPostModal = true">
        <i class="fas fa-plus"></i>
        发布动态
      </button>
    </div>
    <div class="social-feed">
      <div v-for="post in posts" :key="post.id" class="post-item">
        <div class="user-info">
          <div class="avatar"></div>
          <div>
            <h3>{{ post.username }}</h3>
            <p>{{ post.time }}</p>
          </div>
        </div>
        <p class="post-content">{{ post.content }}</p>
        <div class="post-actions">
          <button class="action-btn" @click="likePost(post)">
            <i class="fas fa-heart" :class="{ active: post.isLiked }"></i>
            <span>{{ post.likes }}</span>
          </button>
          <button class="action-btn" @click="showComments(post)">
            <i class="fas fa-comment"></i>
            <span>{{ post.comments }}</span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

interface Post {
  id: number
  username: string
  time: string
  content: string
  likes: number
  comments: number
  isLiked: boolean
}

const showPostModal = ref(false)

const posts: Post[] = [
  {
    id: 1,
    username: '张三',
    time: '5分钟前',
    content: '今天打台球技术突飞猛进！求约球～',
    likes: 12,
    comments: 3,
    isLiked: false
  },
  {
    id: 2,
    username: '李四',
    time: '10分钟前',
    content: '分享一个精彩的走位技巧！',
    likes: 8,
    comments: 5,
    isLiked: true
  }
]

const likePost = (post: Post) => {
  post.isLiked = !post.isLiked
  post.likes += post.isLiked ? 1 : -1
}

const showComments = (post: Post) => {
  console.log('显示评论:', post.id)
  // TODO: 实现评论功能
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

.action-bar {
  margin-bottom: 20px;
}

.post-btn {
  background: linear-gradient(135deg, var(--neon-purple), var(--neon-pink));
  border: none;
  color: white;
  padding: 10px 20px;
  border-radius: 20px;
  display: flex;
  align-items: center;
  gap: 8px;
  cursor: pointer;
  transition: all 0.3s ease;
}

.post-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 0 20px rgba(255, 45, 85, 0.3);
}

.social-feed {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.post-item {
  background: var(--card-bg);
  border-radius: 10px;
  padding: 15px;
  border: 1px solid rgba(0, 255, 255, 0.1);
}

.user-info {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 10px;
}

.avatar {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background: linear-gradient(45deg, var(--neon-pink), var(--neon-purple));
  border: 2px solid var(--neon-blue);
  box-shadow: 0 0 10px var(--neon-blue);
}

.user-info h3 {
  font-size: 16px;
  margin-bottom: 2px;
}

.user-info p {
  font-size: 12px;
  color: rgba(255, 255, 255, 0.6);
}

.post-content {
  margin-bottom: 15px;
  line-height: 1.5;
}

.post-actions {
  display: flex;
  gap: 15px;
}

.action-btn {
  background: none;
  border: none;
  color: rgba(255, 255, 255, 0.6);
  display: flex;
  align-items: center;
  gap: 5px;
  cursor: pointer;
  transition: all 0.3s ease;
}

.action-btn:hover {
  color: var(--neon-pink);
}

.action-btn i {
  font-size: 16px;
}

.action-btn i.active {
  color: var(--neon-pink);
  text-shadow: 0 0 10px var(--neon-pink);
}

.action-btn span {
  font-size: 14px;
}
</style> 