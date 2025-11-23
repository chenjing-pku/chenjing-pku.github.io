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
    /* 自适应列宽，最小320px */
    grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
    gap: 25px;
    width: 100%;
    margin-bottom: 50px;
    margin-top: 20px;
  }

  /* 2. 卡片外观 */
  .custom-resource-card {
    background-color: #ffffff;
    border: 1px solid #e1e4e8;
    border-radius: 8px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.03);
    
    display: flex;
    flex-direction: column;
    justify-content: flex-start; 
    align-items: flex-start;
    text-align: left;
    
    padding: 25px;
    height: 100%; 
    transition: all 0.2s ease-in-out;
  }

  .custom-resource-card:hover {
    transform: translateY(-3px);
    box-shadow: 0 8px 15px rgba(0,0,0,0.1);
    border-color: #0366d6;
  }

  .custom-card-content {
    width: 100%;
    text-align: left;
  }

  /* 3. 标题：大字体、加粗、左对齐 */
  .custom-resource-card a.resource-link {
    display: block;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    font-size: 1.25rem;
    font-weight: 600;
    color: #0366d6;
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
    color: #586069; /* 深灰色 */
    line-height: 1.5;
    text-align: left;
    margin-top: auto; 
    font-style: italic; /* 斜体显示，符合学术惯例 */
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
          {% assign info_text = item.publisher | default: item.description | default: item.venue %}
          
          {{ info_text }}
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
          {% assign info_text = item.publisher | default: item.description | default: item.venue %}
          
          {{ info_text }}
        </div>
      </div>
    </div>
  {% endfor %}
</div>
