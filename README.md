# News Frontend

![Vue](https://img.shields.io/badge/Vue-3-42b883?logo=vue.js&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-7-646cff?logo=vite&logoColor=white)
![Vant](https://img.shields.io/badge/Vant-4-1989fa)
![Pinia](https://img.shields.io/badge/Pinia-Store-f7c948)
![License](https://img.shields.io/badge/License-Learning-lightgrey)

一个基于 Vue 3 + Vite + Vant 的移动端新闻资讯前端项目，包含新闻浏览、分类切换、详情阅读、收藏、历史记录、用户登录注册、主题切换、多语言（中文/英文）以及 AI 问答功能。

## ✨ 项目特性

- 新闻首页：按分类加载新闻列表，支持下拉刷新与上拉加载
- 新闻详情：展示正文、相关推荐，支持收藏
- 用户系统：登录、注册、个人信息、修改密码
- 收藏与历史：支持本地持久化，并可对接后端接口
- AI 问答：流式返回（SSE）聊天内容，支持 Markdown 渲染与安全清洗
- 国际化：支持 `zh-CN` / `en-US` 切换
- 主题系统：内置浅色、深色、蓝色、绿色主题
- 移动端体验：底部 TabBar 导航、Vant 组件化 UI

## 🧱 技术栈

- 框架：Vue 3（Composition API）
- 构建工具：Vite 7
- 路由：Vue Router 4
- 状态管理：Pinia + pinia-plugin-persistedstate
- UI 组件：Vant 4
- HTTP：Axios
- AI 渲染：marked + DOMPurify
- 国际化：vue-i18n

## 🗂️ 目录结构

```text
.
├─ public/
├─ src/
│  ├─ assets/
│  ├─ components/
│  │  ├─ NewsItem.vue
│  │  └─ TabBar.vue
│  ├─ config/
│  │  └─ api.js
│  ├─ i18n/
│  │  ├─ index.js
│  │  └─ locales/
│  ├─ router/
│  ├─ store/
│  │  ├─ modules/
│  │  │  ├─ news.js
│  │  │  ├─ favorite.js
│  │  │  └─ history.js
│  │  ├─ user.js
│  │  ├─ theme.js
│  │  └─ language.js
│  ├─ views/
│  │  ├─ Home.vue
│  │  ├─ NewsDetail.vue
│  │  ├─ AIChat.vue
│  │  ├─ Login.vue / Register.vue
│  │  ├─ Favorite.vue / History.vue
│  │  ├─ My.vue / Profile.vue / Settings.vue
│  │  └─ Category.vue
│  ├─ App.vue
│  └─ main.js
├─ index.html
├─ package.json
└─ vite.config.js
```

## 🚀 本地启动

### 1) 安装依赖

```bash
npm install
```

### 2) 启动开发环境

```bash
npm run dev
```

默认启动后访问终端输出的本地地址（通常为 `http://localhost:5173`）。

### 3) 生产构建

```bash
npm run build
```

### 4) 本地预览构建产物

```bash
npm run preview
```

## 🔌 后端接口说明

当前前端通过 `src/config/api.js` 读取接口地址：

- 新闻接口基础地址：`http://127.0.0.1:8000`
- 主要使用的接口路径包括：
  - `/api/news/categories`
  - `/api/news/list`
  - `/api/news/detail`
  - `/api/user/login`、`/api/user/register`、`/api/user/info`
  - `/api/favorite/*`
  - `/api/history/*`

请确保对应后端服务已启动并允许跨域访问。

## 🤖 AI 问答配置

AI 问答参数同样位于 `src/config/api.js`，包括：

- `apiEndpoint`
- `apiKey`
- `model`

> 安全建议：不要在公开仓库中提交真实 API Key。建议改为环境变量（例如 `.env`）并在代码中读取。

## ☁️ GitHub 上传建议流程

```bash
git init
git add .
git commit -m "chore: initialize toutiao news frontend"
git branch -M main
git remote add origin <你的仓库地址>
git push -u origin main
```

如果你已经初始化过仓库，可从 `git add .` 开始。

## 📄 License

仅用于学习与演示。
