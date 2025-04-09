<template>
  <main class="content">
    <h1>{{ currentCategoryName }} 相关资源</h1>
    <div class="site-grid">
      <div v-for="site in filteredSites" :key="site.id" class="site-card">
        <a :href="site.url" target="_blank">
          <img :src="site.icon" :alt="site.name" class="site-icon" />
          <div class="site-name">{{ site.name }}</div>
        </a>
      </div>
    </div>
  </main>
</template>

<script setup>
import { ref, computed, defineProps, onBeforeMount, onMounted } from 'vue'

const props = defineProps({
  currentCategory2: Number,
})

async function fetchSites() {
  let res = await fetch('https://wxhzhwxhzh.github.io/dpcode/json/vue-url.json')
  let data = await res.text()
  return JSON.parse(data)
}

const allSites = ref(await fetchSites())

onMounted(async () => {
  console.log('123')
})

const filteredSites = computed(() => {
  if (!props.currentCategory2) return allSites.value
  return allSites.value.filter((site) => site.categoryId === props.currentCategory2)
})

const currentCategoryName = computed(() => {
  if (!props.currentCategory2) return '所有'
  const category = sidebarCategories.value.find((c) => c.id === props.currentCategory2)
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
