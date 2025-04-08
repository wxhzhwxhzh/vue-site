<template>
    <footer class="footer">
      <div class="footer-content">
        <div class="footer-section">
          <h3>关于我们</h3>
          <p>这是一个简单的导航网站，帮助开发者快速找到常用资源。</p>
        </div>
        <div class="footer-section">
          <h3>联系方式</h3>
          <p>邮箱: contact@example.com</p>
        </div>
        <div class="footer-section">
          <h3>友情链接</h3>
          <ul>
            <li><a href="https://vuejs.org" target="_blank">Vue.js</a></li>
            <li><a href="https://reactjs.org" target="_blank">React</a></li>
          </ul>
        </div>
      </div>
      <div class="footer-bottom">
        &copy; 2023 我的导航网站. 保留所有权利.
      </div>
    </footer>
  </template>
  
  <script setup>
  </script>
  
  <style scoped>
  .footer {
    background-color: #2c3e50;
    color: white;
    padding: 2rem 0 0;
  }
  
  .footer-content {
    display: flex;
    justify-content: space-around;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 1rem;
  }
  
  .footer-section {
    flex: 1;
    padding: 0 1rem;
  }
  
  .footer-section h3 {
    margin-bottom: 1rem;
    font-size: 1.2rem;
  }
  
  .footer-section p, .footer-section li {
    margin-bottom: 0.5rem;
    color: #ddd;
  }
  
  .footer-section a {
    color: #ddd;
    text-decoration: none;
  }
  
  .footer-section a:hover {
    text-decoration: underline;
  }
  
  .footer-bottom {
    text-align: center;
    padding: 1rem;
    margin-top: 1rem;
    background-color: #1a252f;
    color: #ddd;
  }
  </style>