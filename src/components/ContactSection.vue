<script setup>
import { Mail, MapPin, Send, ExternalLink } from '@lucide/vue'
import GitHubIcon from './icons/GitHubIcon.vue'
import LinkedInIcon from './icons/LinkedInIcon.vue'

const contactLinks = [
  {
    name: 'Email',
    value: 'kpmquockhanh@gmail.com',
    href: 'mailto:kpmquockhanh@gmail.com',
    icon: Mail,
    description: 'For project inquiries and collaborations'
  },
  {
    name: 'GitHub',
    value: 'github.com/kpmquockhanh',
    href: 'https://github.com/kpmquockhanh',
    icon: GitHubIcon,
    description: 'Check out my open source projects'
  },
  {
    name: 'LinkedIn',
    value: 'linkedin.com/in/kpmquockhanh',
    href: 'https://linkedin.com/in/kpmquockhanh',
    icon: LinkedInIcon,
    description: 'Connect with me professionally'
  }
]
</script>

<template>
  <section id="contact" class="py-20 sm:py-24 bg-white">
    <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <h2 class="text-3xl sm:text-4xl font-bold text-primary mb-4">Get in Touch</h2>
        <p class="text-secondary max-w-2xl mx-auto">
          I'm currently open to new opportunities and interesting projects. 
          Whether you need backend architecture, frontend development, or infrastructure setup, let's talk.
        </p>
      </div>
      
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-12">
        <a 
          v-for="link in contactLinks" 
          :key="link.name"
          :href="link.href"
          target="_blank" 
          rel="noopener"
          class="group bg-muted rounded-xl p-6 border border-border hover:border-accent hover:shadow-md transition-all"
        >
          <div class="w-12 h-12 rounded-lg bg-accent-light flex items-center justify-center mb-4 group-hover:bg-accent transition-colors">
            <component :is="link.icon" class="w-6 h-6 text-accent group-hover:text-white transition-colors" />
          </div>
          <h3 class="font-semibold text-primary mb-1">{{ link.name }}</h3>
          <p class="text-sm text-secondary mb-2">{{ link.value }}</p>
          <p class="text-xs text-secondary/70">{{ link.description }}</p>
        </a>
      </div>
      
      <div class="bg-primary rounded-2xl p-8 sm:p-12 text-center text-white">
        <h3 class="text-2xl sm:text-3xl font-bold mb-4">Let's Build Something Together</h3>
        <p class="text-white/80 max-w-xl mx-auto mb-8">
          I specialize in building scalable backend systems, modern web applications, and robust cloud infrastructure.
        </p>
        <div class="flex flex-wrap justify-center gap-4">
          <a 
            href="mailto:kpmquockhanh@gmail.com" 
            class="inline-flex items-center gap-2 px-6 py-3 bg-accent text-white rounded-lg hover:bg-accent/90 transition-colors font-medium"
          >
            <Send class="w-4 h-4" />
            Send an Email
          </a>
          <a 
            href="https://github.com/kpmquockhanh" 
            target="_blank" 
            rel="noopener"
            class="inline-flex items-center gap-2 px-6 py-3 border border-white/30 text-white rounded-lg hover:bg-white/10 transition-colors font-medium"
          >
            <ExternalLink class="w-4 h-4" />
            View GitHub
          </a>
        </div>
      </div>
      
      <div class="mt-16 pt-8 border-t border-border text-center">
        <p class="text-sm text-secondary flex items-center justify-center gap-1">
          <MapPin class="w-4 h-4" />
          Cabramatta West, NSW, Australia · Available for remote work worldwide
        </p>
        <p class="text-xs text-secondary/60 mt-2">
          Built with Vue.js 3, Tailwind CSS, and Vite
        </p>
      </div>
    </div>
  </section>
</template>
