<script setup>
import { Mail, ChevronDown } from '@lucide/vue'
import GitHubIcon from './icons/GitHubIcon.vue'
import LinkedInIcon from './icons/LinkedInIcon.vue'
</script>

<template>
  <section id="hero" class="min-h-screen flex flex-col justify-center items-center px-4 sm:px-6 lg:px-8 bg-white relative">
    <div class="max-w-3xl mx-auto text-center">
      <p class="text-accent font-medium tracking-wide uppercase text-sm mb-4">
        Hello, I'm
      </p>
      <h1 class="text-4xl sm:text-5xl lg:text-6xl font-bold text-primary tracking-tight mb-6">
        Quoc Khanh LUU
      </h1>
      <p class="text-xl sm:text-2xl text-secondary mb-8">
        Full-stack Developer | Open to New Opportunities
      </p>
      <p class="text-base text-secondary/80 max-w-2xl mx-auto mb-10 leading-relaxed">
        Experienced developer with expertise in Go, PHP (Laravel), Vue.js, Node.js, TypeScript, and MySQL.
        Currently building projects with Go microservices, Telegram bots, Discord automation, and React Native apps.
        Proficient in command line, Docker, and cloud infrastructure. Love to learn new things and build automation tools.
      </p>
      <div class="flex flex-wrap justify-center gap-4">
        <a href="#contact" class="inline-flex items-center gap-2 px-6 py-3 bg-primary text-white rounded-lg hover:bg-primary/90 transition-colors">
          <Mail class="w-4 h-4" />
          Get in Touch
        </a>
        <a href="https://github.com/kpmquockhanh" target="_blank" rel="noopener" class="inline-flex items-center gap-2 px-6 py-3 border border-border rounded-lg hover:bg-muted transition-colors">
          <GitHubIcon class="w-4 h-4" />
          GitHub
        </a>
        <a href="https://linkedin.com/in/kpmquockhanh" target="_blank" rel="noopener" class="inline-flex items-center gap-2 px-6 py-3 border border-border rounded-lg hover:bg-muted transition-colors">
          <LinkedInIcon class="w-4 h-4" />
          LinkedIn
        </a>
      </div>
    </div>
    <a href="#skills" class="absolute bottom-8 animate-bounce text-secondary/60 hover:text-secondary transition-colors">
      <ChevronDown class="w-6 h-6" />
    </a>
  </section>
</template>
