# 台球小程序 (Billiards App)

一个基于 Vue 3 + TypeScript 开发的现代化台球小程序，采用赛博朋克风格设计。

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fjiangjiang01%2Fcursorui-table)

## 🌟 特性

- 📱 移动端优先的响应式设计
- 🎮 赛博朋克风格 UI
- 🚀 Vue 3 + TypeScript + Vite
- 📦 Pinia 状态管理
- 🛣 Vue Router 路由管理
- 💫 流畅的动画效果
- 🎯 模块化的组件设计

## 🔥 主要功能

- 🎱 台球技术学习
- 👥 社交约球
- 📅 场馆预约
- 🏆 赛事活动

## 🛠 技术栈

- Vue 3
- TypeScript
- Vite
- Vue Router
- Pinia
- Font Awesome
- CSS3 (赛博朋克风格)

## 📦 安装

```bash
# 克隆项目
git clone https://github.com/jiangjiang01/cursorui-table.git

# 进入项目目录
cd cursorui-table

# 安装依赖
npm install

# 启动开发服务器
npm run dev
```

## 🚀 部署

本项目支持自动部署到 Vercel。只需要：

1. Fork 本项目到你的 GitHub
2. 在 Vercel 中导入项目
3. Vercel 会自动检测到 Vue + Vite 项目并进行相应配置
4. 点击部署即可

### 手动部署配置

如果需要手动配置，请确保：

1. 构建命令设置为：`npm run build`
2. 输出目录设置为：`dist`
3. 安装命令设置为：`npm install`

## 🌈 项目结构

```
src/
├── assets/        # 静态资源
├── components/    # 公共组件
│   └── TabBar.vue # 底部导航栏
├── router/        # 路由配置
├── views/         # 页面组件
│   ├── Home.vue   # 首页
│   ├── Learn.vue  # 学习页面
│   ├── Social.vue # 社交页面
│   └── Profile.vue# 个人中心
└── App.vue        # 根组件
```

## 📝 开发计划

- [ ] 实现视频播放功能
- [ ] 添加用户认证系统
- [ ] 集成后端 API
- [ ] 实现实时聊天功能
- [ ] 添加支付功能

## 🤝 贡献

欢迎提交 issue 和 PR！

## 📄 许可证

[MIT License](LICENSE)
