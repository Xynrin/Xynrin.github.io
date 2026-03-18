---
layout: default
title: Xynrin 的主页
permalink: /
---

<div class="layout-container">
  <!-- 左侧栏：个人信息 -->
  <aside class="sidebar-left">
    <div class="sidebar__profile">
      <img class="avatar" src="https://avatars.githubusercontent.com/u/203426472?u=ef18a376998f0315cda1a14974099134826b6abd&v=4&size=200" alt="Xynrin 头像">
      <h2 class="profile__name">Xynrin</h2>

      <p class="signature-banner" align="center">
        <img
          src="https://capsule-render.vercel.app/api?type=waving&height=140&color=gradient&text=The%20tip%20of%20the%20iceberg%20is%20the%20seed&fontAlign=50&fontAlignY=55&fontSize=24&animation=fadeIn"
          alt="The tip of the iceberg is the seed"
        />
      </p>
    </div>

    <div class="sidebar__social">
      <a class="social-link" href="https://github.com/Xynrin" target="_blank" rel="noopener noreferrer">
        <img class="social-icon" src="https://cdn.simpleicons.org/github" alt="GitHub icon">
        <span>GitHub</span>
      </a>

      <a class="social-link" href="https://gitee.com/Xynrin" target="_blank" rel="noopener noreferrer">
        <img class="social-icon" src="https://cdn.simpleicons.org/gitee" alt="Gitee icon">
        <span>Gitee</span>
      </a>

      <a class="social-link" href="https://qm.qq.com/q/qNY2lPvWkE" target="_blank" rel="noopener noreferrer">
        <img class="social-icon" src="https://cdn.simpleicons.org/qq" alt="QQ icon">
        <span>QQ</span>
      </a>
    </div>
  </aside>

  <!-- 中间主区：横向长图 + 仓库展示 -->
  <main class="main-content">
    <div class="content-banner">
      <img
        src="https://picui.ogmua.cn/s1/2026/03/19/69bad13a56137.webp"
        alt="主页横幅"
      >
    </div>

    <div class="content-header">
      <h1>项目仓库</h1>
      <p class="content-desc">这里集中展示正在维护的仓库、实验项目与阶段性作品。</p>
    </div>

    <div class="repo-grid">
      <article class="repo-card">
        <h3><a href="https://github.com/Xynrin/Xynrin.github.io" target="_blank" rel="noopener noreferrer">Xynrin.github.io</a></h3>
        <p class="repo-meta">GitHub Pages / 个人主页</p>
        <p class="repo-desc">用于部署个人主页与博客内容，持续迭代站点结构、页面样式与内容展示方式。</p>
      </article>

      <article class="repo-card">
        <h3><a href="https://github.com/Xynrin/linux-tool" target="_blank" rel="noopener noreferrer">LINUX-TOOL</a></h3>
        <p class="repo-meta">Open Source / Projects</p>
        <p class="repo-desc">强大的 Linux 工具集，持续整理常用脚本、效率工具与实用功能。</p>
      </article>

      <article class="repo-card">
        <h3><a href="https://gitee.com/Xynrin/linux-tool" target="_blank" rel="noopener noreferrer">Gitee 项目</a></h3>
        <p class="repo-meta">Mirror / 国内托管</p>
        <p class="repo-desc">同步展示部分国内托管项目与代码仓库，方便不同网络环境下访问与协作。</p>
      </article>
    </div>
  </main>

  <!-- 右侧栏：文章列表 -->
  <aside class="sidebar-right">
    <div class="article-panel">
      <h2>文章</h2>
      <p class="article-panel__desc">最近更新</p>

      <ul class="article-list">
        {% for post in site.posts limit:8 %}
          <li class="article-item">
            <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
            <span>{{ post.date | date: "%Y-%m-%d" }}</span>
          </li>
        {% else %}
          <li class="article-item article-item--empty">
            暂无文章，敬请期待 📝
          </li>
        {% endfor %}
      </ul>
    </div>
  </aside>
</div>

.page-content .wrapper,
.wrapper {
  max-width: 1440px !important;
  width: 100% !important;
}

main.page-content {
  max-width: 100% !important;
}

.page-content {
  padding-top: 24px;
}



<style>
  * {
    box-sizing: border-box;
  }

.layout-container {
  display: grid;
  grid-template-columns: 220px minmax(0, 1fr) 260px;
  gap: 1.25rem;
  max-width: 1280px;
  margin: 0 auto;
  padding: 2rem 1rem;
  align-items: start;
}
  .sidebar-left,
  .sidebar-right {
    align-self: start;
    position: sticky;
    top: 1.5rem;
  }

  .sidebar-left,
  .article-panel {
    padding: 1.5rem;
    border-radius: 18px;
    background: #fff;
    box-shadow: 0 10px 30px rgba(15, 23, 42, 0.06);
  }

  .avatar {
    width: 110px;
    height: 110px;
    border-radius: 50%;
    display: block;
    margin: 0 auto 1rem;
    object-fit: cover;
  }

  .profile__name {
    text-align: center;
    margin: 0 0 0.75rem;
    font-size: 1.25rem;
  }

  .signature-banner {
    margin: 0 0 1rem;
  }

  .signature-banner img {
    width: 100%;
    max-width: 100%;
    display: block;
    border-radius: 14px;
  }

  .sidebar__social {
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
  }

  .social-link {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 0.65rem;
    padding: 0.75rem 1rem;
    border-radius: 10px;
    background-color: #f1f5f9;
    color: #1d4ed8;
    font-size: 0.95rem;
    text-align: center;
    text-decoration: none;
    transition: background-color 0.2s ease, transform 0.2s ease;
  }

  .social-link:hover {
    background-color: #e2e8f0;
    transform: translateY(-1px);
  }

  .social-icon {
    width: 18px;
    height: 18px;
    flex-shrink: 0;
  }

.main-content {
  min-width: 0;
  width: 100%;
}
.content-banner {
  margin-bottom: 1.5rem;
  border-radius: 18px;
  overflow: hidden;
  background: #fff;
  box-shadow: 0 10px 30px rgba(15, 23, 42, 0.06);
}

.content-banner img {
  display: block;
  width: 100%;
  height: auto;
}

  .content-header {
    margin-bottom: 1.5rem;
  }

  .content-header h1 {
    margin: 0 0 0.5rem;
    font-size: 2rem;
  }

  .content-desc {
    color: #64748b;
  }

 .repo-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1rem;
}

  .repo-card {
    padding: 1.4rem;
    border-radius: 16px;
    background: #fff;
    box-shadow: 0 10px 30px rgba(15, 23, 42, 0.05);
    transition: transform 0.2s ease, box-shadow 0.2s ease;
  }

  .repo-card:hover {
    transform: translateY(-2px);
    box-shadow: 0 14px 32px rgba(15, 23, 42, 0.08);
  }

  .repo-card h3 {
    margin: 0 0 0.5rem;
  }

  .repo-card h3 a {
    color: #1d4ed8;
    text-decoration: none;
  }

  .repo-meta {
    font-size: 0.88rem;
    color: #94a3b8;
    margin-bottom: 0.8rem;
  }

  .repo-desc {
    color: #475569;
    line-height: 1.7;
  }

  .article-panel h2 {
    margin: 0 0 0.35rem;
    font-size: 1.25rem;
  }

  .article-panel__desc {
    margin: 0 0 1rem;
    color: #64748b;
    font-size: 0.92rem;
  }

  .article-list {
    list-style: none;
    padding: 0;
    margin: 0;
  }

  .article-item {
    padding: 0.85rem 0;
    border-bottom: 1px solid #e2e8f0;
  }

  .article-item:last-child {
    border-bottom: none;
  }

  .article-item a {
    display: block;
    color: #1e293b;
    text-decoration: none;
    font-weight: 600;
    margin-bottom: 0.3rem;
  }

  .article-item a:hover {
    color: #1d4ed8;
  }

  .article-item span {
    font-size: 0.84rem;
    color: #94a3b8;
  }

  .article-item--empty {
    color: #64748b;
    border-bottom: none;
  }

@media (max-width: 1250px) {
  .layout-container {
    grid-template-columns: 220px 1fr;
  }

  .sidebar-right {
    grid-column: 1 / -1;
    position: static;
  }
}

 @media (max-width: 768px) {
  .layout-container {
    grid-template-columns: 1fr;
    padding: 1rem;
  }

  .sidebar-left,
  .sidebar-right {
    position: static;
  }
}
</style>
