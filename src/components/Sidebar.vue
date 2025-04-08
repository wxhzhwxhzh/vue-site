<template>
    <aside class="sidebar">
      <div class="sidebar-header">分类</div>
      <ul class="sidebar-menu">
        <li v-for="category in categories" :key="category.id">
          <a href="#" @click.prevent="selectCategory(category.id)">{{ category.name }}</a>
        </li>
      </ul>
    </aside>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const categories = ref([
    { id: 1, name: '前端开发' },
    { id: 2, name: '后端开发' },
    { id: 3, name: '移动开发' },
    { id: 4, name: '数据库' },
    { id: 5, name: 'DevOps' },
    { id: 6, name: '设计工具' },
  ]);
  
  const selectCategory = (id) => {
    console.log('Selected category:', id);
    // 这里可以触发父组件的事件或更新状态
  };
  </script>
  
  <style scoped>
  .sidebar {
    width: 200px;
    background-color: #f5f5f5;
    padding: 1rem;
    border-right: 1px solid #ddd;
  }
  
  .sidebar-header {
    font-weight: bold;
    margin-bottom: 1rem;
    padding-bottom: 0.5rem;
    border-bottom: 1px solid #ddd;
  }
  
  .sidebar-menu {
    list-style: none;
  }
  
  .sidebar-menu li {
    margin-bottom: 0.5rem;
  }
  
  .sidebar-menu a {
    color: #333;
    text-decoration: none;
    display: block;
    padding: 0.5rem;
    border-radius: 4px;
  }
  
  .sidebar-menu a:hover {
    background-color: #e0e0e0;
  }
  </style>