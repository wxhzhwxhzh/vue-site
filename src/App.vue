<template>
  <div class="app-container">
    <Navbar />
    <div class="main-content">
      <Sidebar @category-change="handleCategoryChange" />
      <MainContent :currentCategory2="currentCategory" />
    </div>
    <Footer />
  </div>
</template>

<script setup>
import Navbar from './components/Navbar.vue'
import Sidebar from './components/Sidebar.vue'
import MainContent from './components/MainContent.vue'
import Footer from './components/Footer.vue'

import { ref, provide } from 'vue'
const currentCategory = ref(null)
// provide('currentCategory', currentCategory)

const handleCategoryChange = (categoryId) => {
  currentCategory.value = categoryId
  console.log('Category changed:', categoryId)
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.main-content {
  display: flex;
  flex: 1;
}
</style>