<template>
  <nav class="navbar">
    <div class="navbar-brand">骚神的导航网站.</div>
    <ul class="navbar-menu">
      <li><a href="#">首页</a></li>
      <li><a href="#">分类</a></li>
      <li><a href="#">收藏</a></li>
      <li><a href="#">关于</a></li>
    </ul>
    <div class="navbar-search">
      <input type="text" placeholder="搜索..." />
      <button>搜索</button>
    </div>
  </nav>
</template>

<script setup></script>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem;
  background-color: #2c3e50;
  color: white;
}

.navbar-brand {
  font-size: 1.5rem;
  font-weight: bold;
}

.navbar-menu {
  display: flex;
  list-style: none;
}

.navbar-menu li {
  margin: 0 1rem;
}

.navbar-menu a {
  color: white;
  text-decoration: none;
}

.navbar-menu a:hover {
  text-decoration: underline;
}

.navbar-search input {
  padding: 0.5rem;
  border: none;
  border-radius: 4px;
}

.navbar-search button {
  padding: 0.5rem 1rem;
  margin-left: 0.5rem;
  border: none;
  border-radius: 4px;
  background-color: #42b983;
  color: white;
  cursor: pointer;
}
</style>
