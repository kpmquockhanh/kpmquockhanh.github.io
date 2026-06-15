<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { Menu, X, Code2 } from '@lucide/vue'

const isScrolled = ref(false)
const isMobileMenuOpen = ref(false)

const navLinks = [
  { name: 'About', href: '#hero' },
  { name: 'Skills', href: '#skills' },
  { name: 'Projects', href: '#projects' },
  { name: 'Experience', href: '#experience' },
  { name: 'Education', href: '#education' },
  { name: 'Contact', href: '#contact' }
]

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

const scrollToSection = (href) => {
  isMobileMenuOpen.value = false
  const element = document.querySelector(href)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <nav 
    class="fixed top-0 left-0 right-0 z-50 transition-all duration-300"
    :class="{ 
      'bg-white/80 backdrop-blur-md shadow-sm border-b border-border': isScrolled,
      'bg-transparent': !isScrolled 
    }"
  >
    <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <!-- Logo -->
        <a href="#hero" @click.prevent="scrollToSection('#hero')" class="flex items-center gap-2 text-primary font-bold text-lg">
          <Code2 class="w-6 h-6 text-accent" />
          <span>Khanh</span>
        </a>
        
        <!-- Desktop Navigation -->
        <div class="hidden md:flex items-center gap-8">
          <a 
            v-for="link in navLinks" 
            :key="link.name"
            :href="link.href"
            @click.prevent="scrollToSection(link.href)"
            class="text-sm font-medium text-secondary hover:text-primary transition-colors"
          >
            {{ link.name }}
          </a>
        </div>
        
        <!-- Mobile Menu Button -->
        <button 
          @click="isMobileMenuOpen = !isMobileMenuOpen"
          class="md:hidden p-2 text-secondary hover:text-primary transition-colors"
        >
          <Menu v-if="!isMobileMenuOpen" class="w-6 h-6" />
          <X v-else class="w-6 h-6" />
        </button>
      </div>
    </div>
    
    <!-- Mobile Menu -->
    <div 
      v-if="isMobileMenuOpen"
      class="md:hidden bg-white border-b border-border shadow-lg"
    >
      <div class="px-4 py-4 space-y-2">
        <a 
          v-for="link in navLinks" 
          :key="link.name"
          :href="link.href"
          @click.prevent="scrollToSection(link.href)"
          class="block px-4 py-2 text-sm font-medium text-secondary hover:text-primary hover:bg-muted rounded-lg transition-colors"
        >
          {{ link.name }}
        </a>
      </div>
    </div>
  </nav>
</template>
