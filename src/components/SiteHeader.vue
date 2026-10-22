<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)
const navLinks = [
  { label: '关于小馆', href: '#story' },
  { label: '时令菜单', href: '#menu' },
  { label: '小馆一隅', href: '#space' },
  { label: '来店里坐坐', href: '#visit' },
]

function closeMenu() {
  isMenuOpen.value = false
}
</script>

<template>
  <header class="site-header">
    <a class="brand" href="#top" aria-label="巷里小馆首页" @click="closeMenu">
      <span class="brand-mark">巷</span>
      <span class="brand-copy"><strong>巷里小馆</strong><small>XIANG LI · JIANGNAN CUISINE</small></span>
    </a>
    <button
      class="menu-toggle"
      type="button"
      :aria-label="isMenuOpen ? '关闭导航' : '打开导航'"
      :aria-expanded="isMenuOpen"
      aria-controls="main-navigation"
      @click="isMenuOpen = !isMenuOpen"
    >
      <span></span><span></span>
    </button>
    <nav id="main-navigation" class="main-nav" :class="{ 'is-open': isMenuOpen }" aria-label="主导航">
      <a v-for="link in navLinks" :key="link.href" :href="link.href" @click="closeMenu">{{ link.label }}</a>
    </nav>
    <a class="header-book" href="#visit" @click="closeMenu">预订座位 <span>↗</span></a>
  </header>
</template>

