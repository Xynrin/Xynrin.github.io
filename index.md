---
layout: home
title: Xynrin 的主页
permalink: /
---

<!-- 新增：网站 Icon（复用 GitHub 头像链接） -->
<link rel="icon" href="https://avatars.githubusercontent.com/u/203426472?u=ef18a376998f0315cda1a14974099134826b6abd&v=4&size=64" type="image/png">
<link rel="shortcut icon" href="https://avatars.githubusercontent.com/u/203426472?u=ef18a376998f0315cda1a14974099134826b6abd&v=4&size=64" type="image/png">

<!-- 整体布局容器 -->
<div class="layout-container">
  <!-- 侧边栏：固定个人信息 -->
  <aside class="sidebar">
    <div class="sidebar__profile">
      <!-- 替换为你的头像地址（建议正方形，尺寸200x200左右） -->
      <img class="avatar" src="https://avatars.githubusercontent.com/u/203426472?u=ef18a376998f0315cda1a14974099134826b6abd&v=4&size=200" alt="Xynrin 头像">
      <h2 class="profile__name">Xynrin</h2>
      <p class="profile__bio">把灵感、项目和日常沉淀成可持续生长的数字花园。</p>
    </div>

    <!-- 可扩展社交链接 -->
    <div class="sidebar__social">
    
      <a class="social-link" href="https://github.com/Xynrin" target="_blank">GitHub</a>
      <a class="social-link" href="https://gitee.com/Xynrin" target="_blank">Gitee</a>
      <a class="social-link" href="https://qm.qq.com/q/qNY2lPvWkE" target="_blank">QQ</a>
    
    </div>
  </aside>

  <!-- 主内容区：展示文章 -->
  <main class="main-content">
    <div class="content-header">
      <h1>最新文章</h1>
      <p class="content-desc">持续整理产品想法、开发记录、设计灵感与个人随笔</p>
    </div>

    <!-- 文章列表 -->
    <ul class="post-list">
      {% for post in site.posts limit:10 %}
        <li class="post-item">
          <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
          <p class="post-meta">{{ post.date | date: "%Y-%m-%d" }}</p>
          {% if post.excerpt %}
            <p class="post-excerpt">{{ post.excerpt | strip_html | truncate: 150 }}</p>
          {% endif %}
        </li>
      {% empty %}
        <!-- 无文章时的提示 -->
        <li class="post-item post-item--empty">
          <p>暂无文章，敬请期待 📝</p>
        </li>
      {% endfor %}
    </ul>
  </main>
</div>

<style>
  /* 全局重置 & 基础样式 */
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  }

  body {
    background-color: #f8fafc;
    color: #1e293b;
    line-height: 1.6;
  }

  a {
    text-decoration: none;
    color: inherit;
  }

  /* 整体布局 */
  .layout-container {
    display: flex;
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem 1rem;
    gap: 2rem;
  }

  /* 侧边栏样式 - 固定+粘性定位 */
  .sidebar {
    width: 280px;
    flex-shrink: 0;
    position: sticky;
    top: 2rem;
    align-self: flex-start;
    padding: 1.5rem;
    border-radius: 12px;
    background-color: #ffffff;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.06);
  }

  /* 头像样式 */
  .avatar {
    width: 120px;
    height: 120px;
    border-radius: 50%;
    object-fit: cover;
    display: block;
    margin: 0 auto 1rem;
    border: 2px solid #f1f5f9;
  }

  /* 个人信息 */
  .profile__name {
    text-align: center;
    font-size: 1.25rem;
    font-weight: 600;
    margin-bottom: 0.5rem;
  }

  .profile__bio {
    text-align: center;
    color: #64748b;
    font-size: 0.95rem;
    margin-bottom: 1.5rem;
  }

  /* 社交链接 */
  .sidebar__social {
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
  }

  .social-link {
    padding: 0.6rem 1rem;
    border-radius: 8px;
    background-color: #f1f5f9;
    color: #1d4ed8;
    font-size: 0.9rem;
    text-align: center;
    transition: background-color 0.2s ease;
  }

  .social-link:hover {
    background-color: #e2e8f0;
  }

  /* 主内容区 */
  .main-content {
    flex: 1;
  }

  .content-header {
    margin-bottom: 2rem;
    padding-bottom: 1rem;
    border-bottom: 1px solid #e2e8f0;
  }

  .content-header h1 {
    font-size: 1.8rem;
    margin-bottom: 0.5rem;
  }

  .content-desc {
    color: #64748b;
    font-size: 1rem;
  }

  /* 文章列表 */
  .post-list {
    list-style: none;
    padding: 0;
  }

  .post-item {
    padding: 1.5rem;
    margin-bottom: 1rem;
    border-radius: 8px;
    background-color: #ffffff;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.04);
    transition: box-shadow 0.2s ease;
  }

  .post-item:hover {
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
  }

  .post-item h3 {
    font-size: 1.2rem;
    margin-bottom: 0.75rem;
    color: #1d4ed8;
  }

  .post-meta {
    color: #94a3b8;
    font-size: 0.85rem;
    margin-bottom: 0.75rem;
  }

  .post-excerpt {
    color: #475569;
    font-size: 0.95rem;
    line-height: 1.7;
  }

  /* 无文章提示 */
  .post-item--empty {
    text-align: center;
    color: #64748b;
    font-size: 1rem;
  }

  /* 移动端适配 */
  @media (max-width: 768px) {
    .layout-container {
      flex-direction: column;
      padding: 1rem;
      gap: 1.5rem;
    }

    .sidebar {
      width: 100%;
      position: static;
      top: auto;
    }

    .content-header h1 {
      font-size: 1.5rem;
    }
  }
</style>

