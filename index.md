---
layout: home
title: Xynrin 的主页
permalink: /
---

<div class="hero">
  <p class="hero__eyebrow">Welcome to Xynrin Blog</p>
  <h1>把灵感、项目和日常沉淀成可持续生长的数字花园。</h1>
  <p class="hero__lead">
    这里会持续整理产品想法、开发记录、设计灵感与个人随笔，
    用更轻盈的方式展示正在进行中的作品与思考。
  </p>
  <div class="hero__actions">
    <a class="button button--primary" href="#latest-posts">查看最新文章</a>
    <a class="button" href="https://github.com/Xynrin">访问 GitHub</a>
  </div>
</div>

## 页面亮点 {#highlights}

<div class="feature-grid">
  <section class="feature-card">
    <h3>🧭 项目导航</h3>
    <p>集中展示正在维护的项目、实验方向与阶段性里程碑，方便快速了解近期重点。</p>
  </section>
  <section class="feature-card">
    <h3>✍️ 内容沉淀</h3>
    <p>将零散灵感整理为清晰文章，记录方案取舍、踩坑复盘和长期学习轨迹。</p>
  </section>
  <section class="feature-card">
    <h3>🚀 持续迭代</h3>
    <p>首页会随着内容更新不断增强，后续还会加入更多专题入口与展示模块。</p>
  </section>
</div>

## 最新文章 {#latest-posts}

<ul class="post-list">
  {% for post in site.posts limit:5 %}
    <li class="post-item">
      <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      <p class="post-meta">{{ post.date | date: "%Y-%m-%d" }}</p>
      {% if post.excerpt %}
        <p>{{ post.excerpt | strip_html | truncate: 120 }}</p>
      {% endif %}
    </li>
  {% endfor %}
</ul>

## 近期计划

- 补充更多文章与项目案例，形成更完整的首页信息架构。
- 优化站点导航与内容分类，让访问路径更清晰。
- 为每个栏目增加独立落地页，逐步扩展为完整个人站点。

<style>
  .hero {
    margin: 1rem 0 2rem;
    padding: 2.5rem;
    border-radius: 24px;
    background: linear-gradient(135deg, #111827, #1d4ed8 55%, #60a5fa);
    color: #fff;
    box-shadow: 0 20px 45px rgba(37, 99, 235, 0.22);
  }

  .hero__eyebrow {
    margin-bottom: 0.75rem;
    font-size: 0.9rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    opacity: 0.8;
  }

  .hero h1 {
    margin-bottom: 1rem;
    font-size: clamp(2rem, 5vw, 3.4rem);
    line-height: 1.15;
  }

  .hero__lead {
    max-width: 42rem;
    font-size: 1.08rem;
    line-height: 1.8;
  }

  .hero__actions {
    display: flex;
    flex-wrap: wrap;
    gap: 0.9rem;
    margin-top: 1.6rem;
  }

  .button {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    padding: 0.78rem 1.25rem;
    border: 1px solid rgba(255, 255, 255, 0.4);
    border-radius: 999px;
    color: #fff;
    text-decoration: none;
    transition: transform 0.2s ease, background 0.2s ease;
  }

  .button:hover {
    background: rgba(255, 255, 255, 0.12);
    transform: translateY(-1px);
  }

  .button--primary {
    background: #fff;
    border-color: #fff;
    color: #1d4ed8;
    font-weight: 600;
  }

  .feature-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 1rem;
    margin: 1.5rem 0 2rem;
  }

  .feature-card {
    padding: 1.35rem;
    border: 1px solid #dbe4ff;
    border-radius: 18px;
    background: linear-gradient(180deg, #ffffff, #f8fbff);
    box-shadow: 0 12px 30px rgba(148, 163, 184, 0.12);
  }

  .feature-card h3 {
    margin-top: 0;
    margin-bottom: 0.6rem;
  }

  .post-list {
    list-style: none;
    padding: 0;
    margin: 1.5rem 0 2rem;
  }

  .post-item {
    padding: 1.2rem 1.3rem;
    margin-bottom: 1rem;
    border: 1px solid #e5e7eb;
    border-radius: 16px;
    background: #fff;
    box-shadow: 0 8px 24px rgba(15, 23, 42, 0.06);
  }

  .post-item h3 {
    margin: 0 0 0.4rem;
  }

  .post-item a {
    text-decoration: none;
    color: #1d4ed8;
  }

  .post-meta {
    margin-bottom: 0.5rem;
    color: #6b7280;
    font-size: 0.92rem;
  }

  @media (max-width: 640px) {
    .hero {
      padding: 1.5rem;
    }

    .hero__actions {
      flex-direction: column;
    }
  }
</style>
