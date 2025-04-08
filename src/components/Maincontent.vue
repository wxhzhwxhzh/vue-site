<template>
    <main class="content">
      <h1>{{ currentCategoryName }} 相关资源</h1>
      <div class="site-grid">
        <div v-for="site in filteredSites" :key="site.id" class="site-card">
          <a :href="site.url" target="_blank">
            <img :src="site.icon" :alt="site.name" class="site-icon">
            <div class="site-name">{{ site.name }}</div>
          </a>
        </div>
      </div>
    </main>
  </template>
  
  <script setup>



  import { ref, computed, defineProps } from 'vue';
  
  const props = defineProps({
    currentCategory2: Number
  })
  
  const allSites = ref([
    { id: 1, name: 'Vue.js', url: 'https://vuejs.org', icon: 'https://vuejs.org/images/logo.png', categoryId: 1 },
    { id: 2, name: 'React', url: 'https://reactjs.org', icon: 'https://reactjs.org/favicon.ico', categoryId: 1 },
    { id: 3, name: 'GitHub', url: 'https://github.com', icon: 'https://github.githubassets.com/favicons/favicon.png', categoryId: 5 },
    { id: 4, name: 'MDN', url: 'https://developer.mozilla.org', icon: 'https://developer.mozilla.org/favicon.ico', categoryId: 1 },
    { id: 5, name: 'MySQL', url: 'https://www.mysql.com', icon: 'https://www.mysql.com/common/logos/logo-mysql-170x115.png', categoryId: 4 },
    { id: 6, name: 'MongoDB', url: 'https://www.mongodb.com', icon: 'https://www.mongodb.com/assets/images/global/favicon.ico', categoryId: 4 },
    { id: 7, name: 'PostgreSQL', url: 'https://www.postgresql.org', icon: 'https://www.postgresql.org/favicon.ico', categoryId: 4 },
    { id: 8, name: 'Stack Overflow', url: 'https://stackoverflow.com', icon: 'https://stackoverflow.com/favicon.ico', categoryId: 1 },
    { id: 9, name: 'CSS Tricks', url: 'https://css-tricks.com', icon: 'https://css-tricks.com/favicon.ico', categoryId: 1 },
    { id: 10, name: '骚神网', url: 'https://wxhzhwxhzh.github.io/sao/', icon: 'https://wxhzhwxhzh.github.io/sao/favicon.ico', categoryId: 6 },
    { id: 11, name: '凡人修仙传', url: 'https://www.bilibili.com/bangumi/play/ss28747?spm_id_from=333.337.0.0', icon: './img/凡人修仙传.jpg', categoryId: 6 },
    { id: 12, name: '仙逆', url: 'https://v.qq.com/x/cover/mzc00200aaogpgh/x4100hntri9.html', icon: './img/仙逆.jpg', categoryId: 6 },
    { id: 13, name: '不良人7', url: 'https://v.qq.com/x/cover/mzc00200s5j9upv/k4100nezibn.html', icon: './img/不良人7.jpg', categoryId: 6 },
  ]);
  
  const filteredSites = computed(() => {
    if (!props.currentCategory2) return allSites.value
    return allSites.value.filter(site => site.categoryId === props.currentCategory2)
  })
  
  const currentCategoryName = computed(() => {
    if (!props.currentCategory2) return '所有'
    const category = sidebarCategories.value.find(c => c.id === props.currentCategory2)
    return category ? category.name : '所有'
  })
  
  const sidebarCategories = ref([
    { id: 1, name: '前端开发' },
    { id: 2, name: '后端开发' },
    { id: 3, name: '移动开发' },
    { id: 4, name: '数据库' },
    { id: 5, name: 'DevOps' },
    { id: 6, name: '动漫相关' },
    { id: 7, name: '动漫' },
  ])
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