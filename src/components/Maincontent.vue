<template>
    <main class="content">
      <h1>欢迎来到我的导航网站</h1>
      <div class="site-grid">
        <div v-for="site in sites" :key="site.id" class="site-card">
          <a :href="site.url" target="_blank">
            <img :src="site.icon" :alt="site.name" class="site-icon">
            <div class="site-name">{{ site.name }}</div>
          </a>
        </div>
      </div>
    </main>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const sites = ref([
    { id: 1, name: 'Vue.js', url: 'https://vuejs.org', icon: 'https://vuejs.org/images/logo.png' },
    { id: 2, name: 'React', url: 'https://reactjs.org', icon: 'https://reactjs.org/favicon.ico' },
    { id: 3, name: 'GitHub', url: 'https://github.com', icon: 'https://github.githubassets.com/favicons/favicon.png' },
    { id: 4, name: 'MDN', url: 'https://developer.mozilla.org', icon: 'https://developer.mozilla.org/favicon.ico' },
    { id: 5, name: 'Stack Overflow', url: 'https://stackoverflow.com', icon: 'https://stackoverflow.com/favicon.ico' },
    { id: 6, name: 'CSS Tricks', url: 'https://css-tricks.com', icon: 'https://css-tricks.com/favicon.ico' },
    { id: 7, name: 'Drissionpage', url: 'https://Drissionpage.cn', icon: 'https://drissionpage.cn/img/color_logo.png' },
    { id: 8, name: 'jd', url: 'https://jd.com', icon: 'https://www.jd.com/favicon.ico' },
  ]);
  </script>
  
  <style scoped>
  .content {
    flex: 1;
    padding: 2rem;
  }
  
  .site-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
    gap: 1.5rem;
    margin-top: 2rem;
  }
  
  .site-card {
    background-color: white;
    border-radius: 8px;
    padding: 1rem;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    transition: transform 0.2s;
  }
  
  .site-card:hover {
    transform: translateY(-5px);
  }
  
  .site-icon {
    width: 48px;
    height: 48px;
    margin-bottom: 0.5rem;
  }
  
  .site-name {
    font-weight: bold;
    color: #333;
  }
  
  .site-card a {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-decoration: none;
  }
  </style>