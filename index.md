---
layout: home
title: Xynrin 的主页
permalink: /
---

<!-- 语义化主容器：替代纯DIV，符合现代前端规范 -->
<main class="modern-home">
  <!-- 英雄区：现代渐变+质感纹理+分层视觉 -->
  <section class="hero">
    <div class="hero__inner">
      <p class="hero__eyebrow">Welcome to Xynrin Blog</p>
      <h1 class="hero__title">把灵感、项目和日常<br>沉淀成可持续生长的数字花园。</h1>
      <p class="hero__lead">
        这里会持续整理产品想法、开发记录、设计灵感与个人随笔，<br>
        用更轻盈的方式展示正在进行中的作品与思考。
      </p>
      <div class="hero__actions">
        <a class="button button--primary" href="#latest-posts">
          <span>查看最新文章</span>
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M14 5l7 7m0 0l-7 7m7-7H3"/>
          </svg>
        </a>
        <a class="button button--secondary" href="https://github.com/Xynrin" target="_blank" rel="noopener">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"/>
          </svg>
          <span>访问 GitHub</span>
        </a>
      </div>
    </div>
  </section>

  <!-- 页面亮点：卡片悬浮动效+现代网格 -->
  <section class="section highlights" id="highlights">
    <h2 class="section__title">页面亮点</h2>
    <div class="feature-grid">
      <article class="feature-card">
        <div class="feature-card__icon">🧭</div>
        <h3 class="feature-card__title">项目导航</h3>
        <p class="feature-card__desc">集中展示正在维护的项目、实验方向与阶段性里程碑，方便快速了解近期重点。</p>
      </article>
      <article class="feature-card">
        <div class="feature-card__icon">✍️</div>
        <h3 class="feature-card__title">内容沉淀</h3>
        <p class="feature-card__desc">将零散灵感整理为清晰文章，记录方案取舍、踩坑复盘和长期学习轨迹。</p>
      </article>
      <article class="feature-card">
        <div class="feature-card__icon">🚀</div>
        <h3 class="feature-card__title">持续迭代</h3>
        <p class="feature-card__desc">首页会随着内容更新不断增强，后续还会加入更多专题入口与展示模块。</p>
      </article>
    </div>
  </section>

  <!-- 最新文章：现代列表+空状态兜底 -->
  <section class="section posts" id="latest-posts">
    <h2 class="section__title">最新文章</h2>
    {% if site.posts.size > 0 %}
      <ul class="post-list">
        {% for post in site.posts limit:5 %}
          <li class="post-item">
            <div class="post-item__header">
              <h3 class="post-item__title">
                <a href="{{ post.url | relative_url }}" class="post-item__link">{{ post.title }}</a>
              </h3>
              <span class="post-item__meta">{{ post.date | date: "%Y-%m-%d" }}</span>
            </div>
            {% if post.excerpt %}
              <p class="post-item__excerpt">{{ post.excerpt | strip_html | truncate: 120 }}</p>
            {% endif %}
          </li>
        {% endfor %}
      </ul>
    {% else %}
      <div class="post-empty">
        <div class="post-empty__icon">✨</div>
        <p class="post-empty__text">暂无发布的文章，敬请期待</p>
      </div>
    {% endif %}
  </section>

  <!-- 近期计划：现代列表样式 -->
  <section class="section plans">
    <h2 class="section__title">近期计划</h2>
    <ul class="plans-list">
      <li class="plans-list__item">
        <span class="plans-list__bullet">▹</span>
        补充更多文章与项目案例，形成更完整的首页信息架构。
      </li>
      <li class="plans-list__item">
        <span class="plans-list__bullet">▹</span>
        优化站点导航与内容分类，让访问路径更清晰。
      </li>
      <li class="plans-list__item">
        <span class="plans-list__bullet">▹</span>
        为每个栏目增加独立落地页，逐步扩展为完整个人站点。
      </li>
    </ul>
  </section>
</main>

<!-- 现代版样式：分层视觉+细腻动效+响应式优化 -->
<style>
  /* 全局基础：现代排版+平滑滚动 */
  :root {
    --primary: #2563eb;
    --primary-light: #3b82f6;
    --primary-dark: #1d4ed8;
    --neutral-50: #f8fafc;
    --neutral-100: #f1f5f9;
    --neutral-200: #e2e8f0;
    --neutral-700: #334155;
    --neutral-800: #1e293b;
    --neutral-900: #0f172a;
    --shadow-sm: 0 2px 6px rgba(14, 21, 47, 0.05);
    --shadow-md: 0 4px 12px rgba(14, 21, 47, 0.08);
    --shadow-lg: 0 8px 24px rgba(14, 21, 47, 0.12);
    --shadow-hover: 0 12px 32px rgba(14, 21, 47, 0.15);
    --radius-sm: 12px;
    --radius-md: 18px;
    --radius-lg: 24px;
    --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  }

  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  html {
    scroll-behavior: smooth;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif;
  }

  body {
    background-color: var(--neutral-50);
    color: var(--neutral-800);
    line-height: 1.6;
  }

  .modern-home {
    max-width: 1000px;
    margin: 0 auto;
    padding: 0 1.5rem;
  }

  /* 通用区块样式 */
  .section {
    margin: 5rem 0;
  }

  .section__title {
    font-size: clamp(1.5rem, 3vw, 2rem);
    font-weight: 700;
    color: var(--neutral-900);
    margin-bottom: 2rem;
    position: relative;
    display: inline-block;
  }

  .section__title::after {
    content: "";
    position: absolute;
    bottom: -8px;
    left: 0;
    width: 60px;
    height: 3px;
    background: linear-gradient(90deg, var(--primary), var(--primary-light));
    border-radius: 3px;
  }

  /* 英雄区：现代渐变+质感+响应式 */
  .hero {
    margin: 3rem 0;
    padding: 4rem 0;
    border-radius: var(--radius-lg);
    background: linear-gradient(135deg, var(--neutral-900) 0%, var(--primary-dark) 50%, var(--primary) 100%);
    color: white;
    position: relative;
    overflow: hidden;
  }

  /* 增加细微噪点纹理，提升质感 */
  .hero::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: url("data:image/svg+xml,%3Csvg width='20' height='20' viewBox='0 0 20 20' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M0 0h20v20H0V0zm2 2v2h2V2H2zm16 0v2h2V2h-2zM2 16v2h2v-2H2zm16 0v2h2v-2h-2z' fill='%23ffffff' fill-opacity='0.03'/%3E%3C/svg%3E");
    opacity: 0.6;
    pointer-events: none;
  }

  .hero__inner {
    position: relative;
    z-index: 1;
    max-width: 800px;
    margin: 0 auto;
    padding: 0 1.5rem;
    text-align: center;
  }

  .hero__eyebrow {
    font-size: 0.95rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    opacity: 0.8;
    margin-bottom: 1.2rem;
    font-weight: 500;
  }

  .hero__title {
    font-size: clamp(2rem, 5vw, 3.5rem);
    line-height: 1.2;
    margin-bottom: 1.5rem;
    font-weight: 800;
  }

  .hero__lead {
    font-size: 1.15rem;
    line-height: 1.8;
    opacity: 0.9;
    margin-bottom: 2.5rem;
    max-width: 600px;
    margin-left: auto;
    margin-right: auto;
  }

  .hero__actions {
    display: flex;
    gap: 1rem;
    justify-content: center;
    flex-wrap: wrap;
  }

  /* 现代按钮：分层+细腻动效 */
  .button {
    display: inline-flex;
    align-items: center;
    gap: 0.6rem;
    padding: 0.9rem 1.8rem;
    border-radius: 999px;
    font-weight: 600;
    text-decoration: none;
    transition: var(--transition);
    border: none;
    cursor: pointer;
    font-size: 1rem;
  }

  .button--primary {
    background: white;
    color: var(--primary-dark);
    box-shadow: var(--shadow-md);
  }

  .button--primary:hover {
    background: var(--neutral-100);
    transform: translateY(-2px);
    box-shadow: var(--shadow-lg);
  }

  .button--secondary {
    background: rgba(255, 255, 255, 0.15);
    color: white;
    border: 1px solid rgba(255, 255, 255, 0.2);
  }

  .button--secondary:hover {
    background: rgba(255, 255, 255, 0.25);
    transform: translateY(-2px);
    box-shadow: var(--shadow-md);
  }

  /* 亮点卡片：现代悬浮+分层 */
  .feature-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.8rem;
  }

  .feature-card {
    background: white;
    border-radius: var(--radius-md);
    padding: 2rem;
    box-shadow: var(--shadow-md);
    transition: var(--transition);
    border: 1px solid var(--neutral-200);
  }

  .feature-card:hover {
    transform: translateY(-6px);
    box-shadow: var(--shadow-hover);
    border-color: var(--primary-light);
  }

  .feature-card__icon {
    font-size: 2rem;
    margin-bottom: 1rem;
    display: block;
  }

  .feature-card__title {
    font-size: 1.25rem;
    font-weight: 600;
    color: var(--neutral-900);
    margin-bottom: 0.8rem;
  }

  .feature-card__desc {
    color: var(--neutral-700);
    line-height: 1.7;
  }

  /* 文章列表：现代样式+空状态 */
  .post-list {
    list-style: none;
    display: grid;
    gap: 1.2rem;
  }

  .post-item {
    background: white;
    border-radius: var(--radius-sm);
    padding: 1.5rem;
    box-shadow: var(--shadow-sm);
    border-left: 3px solid var(--neutral-200);
    transition: var(--transition);
  }

  .post-item:hover {
    border-left-color: var(--primary);
    box-shadow: var(--shadow-md);
  }

  .post-item__header {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin-bottom: 0.8rem;
  }

  .post-item__title {
    font-size: 1.15rem;
    font-weight: 600;
    flex: 1;
  }

  .post-item__link {
    color: var(--neutral-900);
    text-decoration: none;
    position: relative;
  }

  /* 现代渐变下划线动效 */
  .post-item__link::after {
    content: "";
    position: absolute;
    bottom: -2px;
    left: 0;
    width: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--primary), var(--primary-light));
    transition: width 0.3s ease;
    border-radius: 2px;
  }

  .post-item__link:hover::after {
    width: 100%;
  }

  .post-item__meta {
    font-size: 0.85rem;
    color: var(--neutral-700);
    background: var(--neutral-100);
    padding: 0.25rem 0.75rem;
    border-radius: 999px;
  }

  .post-item__excerpt {
    color: var(--neutral-700);
    font-size: 0.95rem;
    line-height: 1.7;
  }

  .post-empty {
    text-align: center;
    padding: 4rem 2rem;
    background: white;
    border-radius: var(--radius-md);
    box-shadow: var(--shadow-sm);
    border: 1px dashed var(--neutral-200);
  }

  .post-empty__icon {
    font-size: 3rem;
    margin-bottom: 1rem;
  }

  .post-empty__text {
    font-size: 1.1rem;
    color: var(--neutral-700);
  }

  /* 计划列表：现代样式 */
  .plans-list {
    list-style: none;
    display: grid;
    gap: 1rem;
  }

  .plans-list__item {
    display: flex;
    align-items: flex-start;
    gap: 1rem;
    font-size: 1.05rem;
    color: var(--neutral-700);
    padding: 1rem;
    background: white;
    border-radius: var(--radius-sm);
    box-shadow: var(--shadow-sm);
    transition: var(--transition);
  }

  .plans-list__item:hover {
    box-shadow: var(--shadow-md);
    transform: translateX(4px);
  }

  .plans-list__bullet {
    color: var(--primary);
    font-weight: 700;
    line-height: 1.6;
  }

  /* 响应式优化：移动端适配 */
  @media (max-width: 768px) {
    .section {
      margin: 3rem 0;
    }

    .hero {
      padding: 3rem 0;
      margin: 2rem 0;
    }

    .hero__title {
      font-size: clamp(1.8rem, 5vw, 2.8rem);
    }

    .hero__actions {
      flex-direction: column;
      align-items: center;
    }

    .button {
      width: 100%;
      justify-content: center;
    }

    .feature-grid {
      grid-template-columns: 1fr;
    }

    .post-item__header {
      flex-direction: column;
      gap: 0.8rem;
    }

    .post-item__meta {
      align-self: flex-start;
    }
  }

  @media (max-width: 480px) {
    .modern-home {
      padding: 0 1rem;
    }

    .hero__inner {
      padding: 0 1rem;
    }

    .feature-card {
      padding: 1.5rem;
    }

    .post-item, .plans-list__item {
      padding: 1.2rem;
    }
  }
</style>

