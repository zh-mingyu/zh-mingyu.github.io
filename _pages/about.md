---
permalink: /
title: ""
excerpt: ""
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

{% if site.google_scholar_stats_use_cdn %}
{% assign gsDataBaseUrl = "https://cdn.jsdelivr.net/gh/" | append: site.repository | append: "@" %}
{% else %}
{% assign gsDataBaseUrl = "https://raw.githubusercontent.com/" | append: site.repository | append: "/" %}
{% endif %}
{% assign url = gsDataBaseUrl | append: "google-scholar-stats/gs_data_shieldsio.json" %}

<style>
  /* Core UI & Bilingual Styles */
  .research-intro { font-size: 1.02em; line-height: 1.72; color: #24292e; margin-bottom: 1rem; }
  .research-intro strong { color: #012F63; }
  .language-switcher { margin: 1rem 0 1.4rem 0; }
  .language-tabs { display: inline-flex; gap: 0.35rem; padding: 0.28rem; border-radius: 999px; background: #f6f8fa; border: 1px solid rgba(1,47,99,0.08); box-shadow: 0 4px 14px rgba(1,47,99,0.05); margin-bottom: 1rem; }
  .lang-tab { border: 0; border-radius: 999px; padding: 0.42rem 0.92rem; background: transparent; color: #586069; font-size: 0.86rem; font-weight: 850; cursor: pointer; transition: all 0.2s ease; }
  .lang-tab:hover, .lang-tab.active { color: #fff; background: linear-gradient(135deg, #ff4d6d 0%, #ff7eb3 100%); box-shadow: 0 6px 16px rgba(255,77,109,0.2); }
  .lang-panel { display: none; }
  .lang-panel.active { display: block; }
  
  /* Bilingual toggles */
  .i18n-zh, .i18n-zh-inline { display: none !important; }
  body.lang-zh .i18n-en, body.lang-zh .i18n-en-inline { display: none !important; }
  body.lang-zh .i18n-zh { display: block !important; }
  body.lang-zh .i18n-zh-inline { display: inline !important; }
  body.lang-en .i18n-en { display: block !important; }
  body.lang-en .i18n-en-inline { display: inline !important; }

  /* Sections */
  .open-science-note { margin: 1rem 0 1.8rem 0; padding: 1rem 1.1rem; border-left: 4px solid #ff4d6d; border-radius: 12px; background: linear-gradient(180deg, #fff5f7 0%, #ffffff 100%); box-shadow: 0 6px 18px rgba(255,77,109,0.06); color: #012F63; }
  .opensource-section, .news-section { margin: 2rem 0 2.2rem 0; padding: 1.2rem; border-radius: 18px; border: 1px solid rgba(1,47,99,0.05); background: #ffffff; box-shadow: 0 10px 30px rgba(0,0,0,0.04); }
  .section-kicker { display: inline-flex; align-items: center; gap: 0.45rem; padding: 0.28rem 0.75rem; border-radius: 999px; background: rgba(255,77,109,0.1); color: #ff4d6d; font-size: 0.78rem; font-weight: 800; letter-spacing: 0.02em; text-transform: uppercase; }
  .opensource-title, .news-title { margin: 0.65rem 0 0.3rem 0; color: #012F63; font-size: 1.45rem; font-weight: 850; }
  
  /* Projects Grid */
  .opensource-grid { display: grid; grid-template-columns: repeat(3, minmax(0, 1fr)); gap: 0.85rem; padding-right: 0.35rem; }
  .opensource-card { display: flex; flex-direction: column; align-items: center; text-align: center; min-height: 225px; padding: 1rem 0.85rem; border-radius: 15px; border: 1px solid rgba(0,0,0,0.06); background: #fff; box-shadow: 0 6px 18px rgba(0,0,0,0.03); transition: transform 0.24s ease, border-color 0.24s, box-shadow 0.24s; }
  .opensource-card:hover { transform: translateY(-6px); border-color: rgba(255,77,109,0.3); box-shadow: 0 14px 32px rgba(255,77,109,0.12); }
  .opensource-card img { width: auto; height: 98px; max-width: 80%; object-fit: contain; border-radius: 8px; margin-bottom: 0.75rem; }
  .opensource-card-title { color: #012F63; font-size: 0.95rem; font-weight: 850; margin-bottom: 0.25rem; }
  .opensource-card-meta { color: #ff4d6d; font-size: 0.78rem; font-weight: 750; margin-bottom: 0.4rem; }
  .opensource-card-links a { display: inline-flex; padding: 0.18rem 0.52rem; border-radius: 999px; border: 1px solid rgba(255,77,109,0.3); background: rgba(255,77,109,0.05); color: #ff4d6d !important; font-size: 0.72rem; font-weight: 700; text-decoration: none !important; margin: 0.15rem; transition: all 0.2s; }
  .opensource-card-links a:hover { background: #ff4d6d; color: #fff !important; }

  /* News */
  .news-grid { display: grid; grid-template-columns: 1fr; gap: 0.75rem; max-height: 400px; overflow-y: auto; padding-right: 0.35rem; }
  .news-card { display: grid; grid-template-columns: 6.8rem 1fr; gap: 0.8rem; align-items: start; padding: 0.9rem 0.95rem; border-radius: 14px; border: 1px solid rgba(0,0,0,0.05); background: #fff; box-shadow: 0 6px 18px rgba(0,0,0,0.03); transition: transform 0.22s ease; }
  .news-card:hover { transform: translateY(-4px); border-color: rgba(255,77,109,0.2); }
  .news-date { display: inline-flex; justify-content: center; padding: 0.26rem 0.5rem; border-radius: 999px; color: #fff; background: linear-gradient(135deg, #ff4d6d 0%, #ff7eb3 100%); font-size: 0.78rem; font-weight: 850; }
  .news-text { color: #24292e; font-size: 0.92rem; line-height: 1.55; }
  
  /* Filter System */
  #filter-container { margin: 20px 0; display: flex; flex-wrap: wrap; gap: 8px; }
  .filter-btn { padding: 6px 14px; border: 1px solid #e1e4e8; border-radius: 20px; background-color: #f6f8fa; color: #586069; font-size: 0.85em; font-weight: 600; cursor: pointer; transition: all 0.2s; }
  .filter-btn.active { background: linear-gradient(135deg, #ff4d6d, #ff7eb3); color: white; border-color: transparent; box-shadow: 0 4px 10px rgba(255,77,109,0.3); }
  
  /* 🌟 Paper Box Styles (1:1 Reference Match) 🌟 */
  .floating-card { transition: opacity 0.3s ease, transform 0.3s ease; }
  .paper-box {
    display: flex;
    flex-direction: row;
    gap: 28px;
    padding: 24px;
    margin-bottom: 24px;
    border-radius: 16px;
    background: #ffffff;
    border: 1px solid rgba(255,77,109,0.15) !important;
    box-shadow: 0 8px 24px rgba(255,77,109,0.08) !important;
    align-items: flex-start;
  }
  .paper-box:hover {
    transform: translateY(-4px);
    box-shadow: 0 12px 32px rgba(255,77,109,0.18) !important;
    border: 1px solid rgba(255,77,109,0.35) !important;
  }
  
  .paper-box-image {
    width: 42%;
    flex-shrink: 0;
    position: relative;
  }
  .paper-box-image img {
    width: 100%;
    border-radius: 8px;
    border: 1px solid #eaecef;
    box-shadow: 0 4px 12px rgba(0,0,0,0.06);
    display: block;
  }
  
  .badge {
    position: absolute;
    top: -1px;
    left: -1px;
    background: linear-gradient(135deg, #ff4d6d 0%, #ff7eb3 100%);
    color: #fff;
    padding: 5px 14px;
    font-size: 0.85em;
    font-weight: 850;
    border-radius: 8px 0 12px 0;
    z-index: 10;
    box-shadow: 2px 2px 10px rgba(255,77,109,0.4);
    letter-spacing: 0.5px;
  }
  
  .paper-box-text {
    width: 58%;
    display: flex;
    flex-direction: column;
  }
  
  .paper-title {
    font-size: 1.25em;
    font-weight: 850;
    color: #012F63;
    margin-bottom: 8px;
    line-height: 1.35;
  }
  
  .paper-venue {
    font-size: 0.95em;
    font-style: italic;
    color: #586069;
    margin-bottom: 14px;
  }
  
  .paper-authors {
    font-size: 1.05em;
    color: #24292e;
    margin-bottom: 18px;
    line-height: 1.6;
    font-weight: 600;
  }
  .paper-authors a {
    color: #012F63;
    text-decoration: none;
  }
  .paper-authors a:hover {
    text-decoration: underline;
  }
  
  /* Pink/Purple Gradient Highlight for Author */
  .author-self {
    font-weight: 850 !important;
    font-style: italic;
    background: linear-gradient(135deg, #d500f9 0%, #ff1744 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    font-size: 1.05em;
  }
  
  .badge-container {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-bottom: 18px;
  }
  .inner-tag-badge {
    font-size: 0.82em;
    padding: 4px 12px;
    background-color: #f3f4f6;
    color: #374151;
    border-radius: 8px;
    border: 1px solid #e5e7eb;
    font-weight: 500;
  }
  
  .paper-link-container {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
  }
  .paper-link-btn {
    font-size: 0.88em;
    padding: 6px 18px;
    background: linear-gradient(135deg, #ff4d6d 0%, #ff758c 100%);
    color: #ffffff !important;
    border-radius: 999px;
    font-weight: 850;
    text-decoration: none !important;
    border: none !important;
    box-shadow: 0 4px 12px rgba(255, 77, 109, 0.35);
    transition: transform 0.2s, box-shadow 0.2s, filter 0.2s;
  }
  .paper-link-btn:hover {
    transform: translateY(-2px);
    box-shadow: 0 6px 16px rgba(255, 77, 109, 0.45);
    filter: brightness(1.05);
  }

  @media (max-width: 800px) { 
    .paper-box { flex-direction: column; gap: 16px; padding: 18px; }
    .paper-box-image, .paper-box-text { width: 100%; }
    .opensource-grid { grid-template-columns: 1fr; } 
  }
</style>

<span class="anchor" id="about-me"></span>

# Hi, I am Mingyu Zhang (张明宇).

<div class="language-switcher" id="research-language-switcher">
  <div class="language-tabs" role="tablist">
    <button class="lang-tab active" type="button" data-lang="en" role="tab" aria-selected="true">English</button>
    <button class="lang-tab" type="button" data-lang="zh" role="tab" aria-selected="false">中文</button>
  </div>
  
  <div class="lang-panel active" data-lang-panel="en" role="tabpanel">
    <div class="research-intro">
      <p>Welcome to my homepage! I'm currently an Undergrad student in the <a href="https://www.sc.sdu.edu.cn">School of Software</a>, <a href="https://www.sdu.edu.cn">Shandong University</a>, under the supervision of Prof. <a href="https://liqiangnie.github.io/index.html">Liqiang Nie</a> and Prof. <a href="https://faculty.sdu.edu.cn/huyupeng1/zh_CN/index.htm">Yupeng Hu</a>.</p>
      <p>My research interests include <strong>Multimodal Large Language Models, robust representation learning, and trustworthy AI</strong>.</p>
    </div>
  </div>
  
  <div class="lang-panel" data-lang-panel="zh" role="tabpanel">
    <div class="research-intro">
      <p>欢迎来到我的主页！我目前是山东大学<a href="https://www.sc.sdu.edu.cn">软件学院</a>的本科生，师从 Prof. <a href="https://liqiangnie.github.io/index.html">Liqiang Nie</a> 与 Prof. <a href="https://faculty.sdu.edu.cn/huyupeng1/zh_CN/index.htm">Yupeng Hu</a>。</p>
      <p>我的研究兴趣包括<strong>多模态大语言模型、鲁棒表征学习与可信AI研究</strong>。</p>
    </div>
  </div>
</div>

<div class="open-science-note">
  <div class="i18n-en">
    <p>I am a strong advocate for open science. All the projects I have been primarily involved in have been fully open-sourced. We warmly invite you to explore our projects, share your feedback, and connect with us for further discussion!</p>
  </div>
  <div class="i18n-zh">
    <p>我是开放科学的坚定拥趸，主要参与的项目均已全面开源。欢迎大家访问我们的项目主页，非常期待听到您的真实反馈，随时欢迎找我交流探讨！</p>
  </div>
</div>

<div class="opensource-section" id="open-source-projects">
  <div class="section-kicker">
    <span class="i18n-en-inline">💻 Open Science</span>
    <span class="i18n-zh-inline">💻 开放科学</span>
  </div>
  <div class="opensource-title">
    <span class="i18n-en-inline">Projects</span>
    <span class="i18n-zh-inline">项目主页</span>
  </div>
  <div class="opensource-grid">
    <div class="opensource-card">
      <img src="images/hint-logo.png" alt="HINT">
      <div class="opensource-card-title">HINT</div>
      <div class="opensource-card-meta"><span class="i18n-en-inline">ICASSP 2026</span><span class="i18n-zh-inline">ICASSP 2026</span></div>
      <div class="opensource-card-links">
        <a href="https://arxiv.org/abs/2603.26341" target="_blank">Paper</a>
        <a href="https://zh-mingyu.github.io/HINT.github.io/" target="_blank">Project</a>
        <a href="https://github.com/zh-mingyu/HINT" target="_blank">Code</a>
      </div>
    </div>
    <div class="opensource-card">
      <img src="images/consep-logo.png" alt="ConeSep">
      <div class="opensource-card-title">ConeSep</div>
      <div class="opensource-card-meta"><span class="i18n-en-inline">CVPR 2026</span><span class="i18n-zh-inline">CVPR 2026</span></div>
      <div class="opensource-card-links">
        <a href="https://arxiv.org/abs/2604.20358" target="_blank">Paper</a>
        <a href="https://lee-zixu.github.io/ConeSep.github.io/" target="_blank">Project</a>
        <a href="https://github.com/Lee-zixu/ConeSep" target="_blank">Code</a>
      </div>
    </div>
  </div>
</div>

<div class="news-section" id="news">
  <div class="section-kicker">
    <span class="i18n-en-inline">🔥 Updates</span>
    <span class="i18n-zh-inline">🔥 最新动态</span>
  </div>
  <div class="news-title">
    <span class="i18n-en-inline">News</span>
    <span class="i18n-zh-inline">新闻动态</span>
  </div>
  <div class="news-grid">
    <div class="news-card">
      <div class="news-date">2026.03.03</div>
      <div class="news-text">🎉🎉 One paper was accepted by <strong>CVPR 2026</strong>! Congratulations to all co-authors!</div>
    </div>
    <div class="news-card">
      <div class="news-date">2026.01.18</div>
      <div class="news-text">🎉🎉 One paper has been accepted to <strong>ICASSP 2026</strong>! Congratulations to our co-authors!</div>
    </div>
    <div class="news-card">
      <div class="news-date">2025.10.18</div>
      <div class="news-text">🏆 As the core member, our team wins the <strong>Grand Prize</strong> in the CICAS Smart Power Scenario Competition. Congratulations to all team members!</div>
    </div>
  </div>
</div>

# 📝 Publications

<div class="paper-note">⚓️ denotes project leader; 📧 denotes corresponding author.</div>

<div id="publications-wrapper">
  <div id="filter-container">
    <!-- Filter buttons will be auto-generated by JS -->
  </div>

  <!-- ConeSep Paper Box -->
  <div class="paper-box floating-card" data-tags="CVPR 2026, Multimodal Understanding, Robustness">
    <div class="paper-box-image">
      <div class="badge">CVPR 2026</div>
      <img src="images/ConeSep-CVPR26.png" alt="ConeSep">
    </div>
    <div class="paper-box-text">
      <div class="paper-title">ConeSep: Cone-based Robust Noise-Unlearning Compositional Network for Composed Image Retrieval</div>
      <div class="paper-venue">IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR 2026)</div>
      <div class="paper-authors">
        <a href="https://lee-zixu.github.io">Zixu Li</a>, 
        <a href="https://faculty.sdu.edu.cn/huyupeng1/zh_CN/index.htm">Yupeng Hu</a>📧, 
        <a href="https://zivchen-ty.github.io/">Zhiwei Chen</a>, 
        <a href="https://zh-mingyu.github.io/" class="author-self">Mingyu Zhang</a>, 
        <a href="https://zhihfu.github.io">Zhiheng Fu</a>, 
        <a href="https://liqiangnie.github.io/index.html">Liqiang Nie</a>
      </div>
      <div class="badge-container">
        <span class="inner-tag-badge">CVPR 2026</span>
        <span class="inner-tag-badge">Multimodal Understanding</span>
        <span class="inner-tag-badge">Robustness</span>
      </div>
      <div class="paper-link-container">
        <a href="https://arxiv.org/abs/2604.20358" class="paper-link-btn">[Paper]</a>
        <a href="https://lee-zixu.github.io/ConeSep.github.io/" class="paper-link-btn">[Website]</a>
        <a href="https://github.com/Lee-zixu/ConeSep" class="paper-link-btn">[Code]</a>
      </div>
    </div>
  </div>

  <!-- HINT Paper Box -->
  <div class="paper-box floating-card" data-tags="ICASSP 2026, First Author, Multimodal Understanding">
    <div class="paper-box-image">
      <div class="badge">ICASSP 2026</div>
      <img src="images/HINT-ICASSP26.png" alt="HINT">
    </div>
    <div class="paper-box-text">
      <div class="paper-title">HINT: Composed Image Retrieval with Dual-Path Compositional Contextualized Network</div>
      <div class="paper-venue">IEEE International Conference on Acoustics, Speech, and Signal Processing (ICASSP 2026)</div>
      <div class="paper-authors">
        <a href="https://zh-mingyu.github.io/" class="author-self">Mingyu Zhang</a>, 
        <a href="https://lee-zixu.github.io">Zixu Li</a>, 
        <a href="https://zivchen-ty.github.io/">Zhiwei Chen</a>, 
        <a href="https://zhihfu.github.io">Zhiheng Fu</a>, 
        Xiaowei Zhu, Jiajia Nie, 
        <a href="https://weiyinwei.github.io">Yinwei Wei</a>, 
        <a href="https://faculty.sdu.edu.cn/huyupeng1/zh_CN/index.htm">Yupeng Hu</a>📧
      </div>
      <div class="badge-container">
        <span class="inner-tag-badge">ICASSP 2026</span>
        <span class="inner-tag-badge">First Author</span>
        <span class="inner-tag-badge">Multimodal Understanding</span>
      </div>
      <div class="paper-link-container">
        <a href="https://arxiv.org/abs/2603.26341" class="paper-link-btn">[Paper]</a>
        <a href="https://zh-mingyu.github.io/HINT.github.io/" class="paper-link-btn">[Website]</a>
        <a href="https://github.com/zh-mingyu/HINT" class="paper-link-btn">[Code]</a>
      </div>
    </div>
  </div>

</div>

# 🏆 Honors and Awards
*   *2025.10*, **Grand Prize** in the CICAS Smart Power Scenario Competition.

# 📖 Educations
*   *2023.09 - Present*, Undergrad in the School of Software, Shandong University.


<script>
document.addEventListener('DOMContentLoaded', function() {
  // 1. Language Switcher
  const languageSwitcher = document.getElementById('research-language-switcher');
  if (languageSwitcher) {
    const tabs = languageSwitcher.querySelectorAll('.lang-tab');
    const panels = languageSwitcher.querySelectorAll('.lang-panel');
    const setLanguage = (lang) => {
      document.body.classList.toggle('lang-en', lang === 'en');
      document.body.classList.toggle('lang-zh', lang === 'zh');
      tabs.forEach(tab => {
        const active = tab.dataset.lang === lang;
        tab.classList.toggle('active', active);
        tab.setAttribute('aria-selected', active ? 'true' : 'false');
      });
      panels.forEach(panel => {
        panel.classList.toggle('active', panel.dataset.langPanel === lang);
      });
    };
    setLanguage('en');
    tabs.forEach(tab => {
      tab.addEventListener('click', () => setLanguage(tab.dataset.lang));
    });
  }

  // 2. Paper Tags Filter
  const wrapper = document.getElementById('publications-wrapper');
  const filterContainer = document.getElementById('filter-container');
  if (!wrapper || !filterContainer) return;

  const paperBoxes = Array.from(wrapper.querySelectorAll('.paper-box'));
  let tagCounts = {};
  let activeTags = new Set();

  paperBoxes.forEach((box, index) => {
    box.dataset.originalOrder = String(index);
    const tagsAttribute = box.getAttribute('data-tags');
    if (tagsAttribute) {
      tagsAttribute.split(',').forEach(t => {
        const tag = t.trim();
        if (tag) tagCounts[tag] = (tagCounts[tag] || 0) + 1;
      });
    }
  });

  const tagOrder = ['First Author', 'CVPR 2026', 'ICASSP 2026', 'Multimodal Understanding', 'Robustness'];
  const sortedTags = Object.keys(tagCounts).sort((a, b) => {
    const ia = tagOrder.indexOf(a);
    const ib = tagOrder.indexOf(b);
    if (ia !== -1 && ib !== -1) return ia - ib;
    if (ia !== -1) return -1;
    if (ib !== -1) return 1;
    return a.localeCompare(b);
  });

  sortedTags.forEach(tag => {
    const btn = document.createElement('button');
    btn.className = 'filter-btn';
    btn.textContent = `${tag} (${tagCounts[tag]})`;
    btn.onclick = () => {
      if (activeTags.has(tag)) {
        activeTags.delete(tag);
        btn.classList.remove('active');
      } else {
        activeTags.add(tag);
        btn.classList.add('active');
      }
      filterPapers();
    };
    filterContainer.appendChild(btn);
  });

  function filterPapers() {
    paperBoxes.forEach(box => {
      const boxTagsString = box.getAttribute('data-tags');
      const boxTags = boxTagsString ? boxTagsString.split(',').map(t => t.trim()) : [];
      const isMatched = activeTags.size === 0 || Array.from(activeTags).every(activeTag => boxTags.includes(activeTag));
      
      box.style.opacity = activeTags.size > 0 && !isMatched ? '0.25' : '1';
      box.style.transform = activeTags.size > 0 && !isMatched ? 'scale(0.98)' : 'scale(1)';
      
      box.querySelectorAll('.inner-tag-badge').forEach(badge => {
        badge.classList.toggle('active', activeTags.has(badge.textContent));
      });
    });
  }
});
</script>
