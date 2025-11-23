---
title: Resources
nav:
  order: 3
  tooltip: Software, datasets, and more
---

<style>
  /* 1. 强制网格布局 */
  .custom-grid-container {
    display: grid;
    /* 每列最小320px，不够放就换行 */
    grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
    gap: 25px;
    width: 100%;
    margin-bottom: 50px;
    margin-top: 20px;
  }

  /* 2. 卡片外观：强制左对齐 */
  .custom-resource-card {
    background-color: #ffffff;
    border: 1px solid #e1e4e8;
    border-radius: 8px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.03);
    
    display: flex;
    flex-direction: column;
    /* ★ 核心：强制所有内容左对齐 */
    justify-content: flex-start; 
    align-items: flex-start;
    text-align: left;
    
    padding: 25px;
    height: 100%; /* 撑满高度 */
    transition: all 0.2s ease-in-out;
  }

  /* 悬停加深效果 */
  .custom-resource-card:hover {
    transform: translateY(-3px);
    box-shadow: 0 8px 15px rgba(0,0,0,0.1);
    border-color: #0366d6;
  }

  .custom-card-content {
    width: 100%;
    text-align: left; /* 双重保险：强制左对齐 */
  }

  /* 3. 标题：大字体、加粗 */
  .custom-resource-card a.resource-link {
    display: block;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    font-size: 1.25rem;  /* ★ 字体加大到 1.25倍 */
    font-weight: 600;    /* 加粗 */
    color: #0366d6;      /* 蓝色 */
    text-decoration: none;
    line-height: 1.4;
    margin-bottom: 12px;
    text-align: left;
  }

  .custom-resource-card a.resource-link:hover {
    text-decoration: underline;
  }

  /* 4. 期刊年份信息 */
  .custom-card-meta {
    font-size: 0.95rem;
    color: #586069;
    line-height: 1.5;
    text-align: left;
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    align-items: center;
  }

  .venue-badge {
    font-weight: 500;
    color: #24292e; /* 深黑色字体 */
  }
  
  .year-badge {
    color: #6a737d;
  }
</style>

<h1>{% include icon.html icon="fa-solid fa-wrench" %}Resources</h1>

<h2>Code</h2>

<div class="custom-grid-container">
  {% assign code_items = site.data.projects | where: "group", "code" %}
  {% for item in code_items %}
    <div class="custom-resource-card">
      <div class="custom-card-content">
        <a class="resource-link" href="{{ item.url | default: item.pdf | default: item.redirect | default: item.link | default: '#' }}" target="_blank">
          {{ item.title }}
        </a>
        
        <div class="custom-card-meta">
          {% assign venue_text = item.venue | default: item.publication | default: item.journal | default: item.conference %}
          
          {% if venue_text %}
            <span class="venue-badge">{{ venue_text }}</span>
          {% endif %}
          
          {% if venue_text and item.year %}
            <span class="year-badge">, {{ item.year }}</span>
          {% elsif item.year %}
            <span class="year-badge">{{ item.year }}</span>
          {% endif %}
        </div>
      </div>
    </div>
  {% endfor %}
</div>

{% include section.html %}

<h2>Data</h2>

<div class="custom-grid-container">
  {% assign data_items = site.data.projects | where: "group", "data" %}
  {% for item in data_items %}
    <div class="custom-resource-card">
      <div class="custom-card-content">
        <a class="resource-link" href="{{ item.url | default: item.pdf | default: item.redirect | default: item.link | default: '#' }}" target="_blank">
          {{ item.title }}
        </a>
        
        <div class="custom-card-meta">
          {% assign venue_text = item.venue | default: item.publication | default: item.journal | default: item.conference %}
          
          {% if venue_text %}
            <span class="venue-badge">{{ venue_text }}</span>
          {% endif %}
          
          {% if venue_text and item.year %}
            <span class="year-badge">, {{ item.year }}</span>
          {% elsif item.year %}
            <span class="year-badge">{{ item.year }}</span>
          {% endif %}
        </div>
      </div>
    </div>
  {% endfor %}
</div>
