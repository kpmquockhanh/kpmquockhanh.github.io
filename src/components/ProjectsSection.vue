<script setup>
import { ExternalLink, Code2 } from '@lucide/vue'
import GitHubIcon from './icons/GitHubIcon.vue'

const projects = [
  {
    title: 'Gemini Telegram Bot',
    description: 'AI-powered Telegram chatbot integrating Google\'s Gemini API for intelligent conversations. Built with Go for high-performance message handling and concurrent user sessions.',
    tags: ['Go', 'AI/ML', 'Telegram API', 'Gemini'],
    github: 'https://github.com/kpmquockhanh/gemini-telegram',
    demo: null,
    featured: true
  },
  {
    title: 'CookMate App',
    description: 'Cross-platform mobile cooking application built with React Native and TypeScript. Features AI-powered hands-free voice interactions for recipe navigation, step-by-step cooking guidance, and ingredient management. Includes recipe management, meal planning, and grocery list generation.',
    tags: ['React Native', 'TypeScript', 'AI', 'Voice Recognition', 'Mobile', 'iOS', 'Android'],
    github: 'https://github.com/kpmquockhanh/cook-mate-rn',
    demo: null,
    featured: true
  },
  {
    title: 'CircArts',
    description: 'Creative arts and digital content platform. Built with JavaScript to showcase artistic projects and creative works.',
    tags: ['JavaScript', 'Web', 'Creative', 'Frontend'],
    github: 'https://github.com/kpmquockhanh/circarts-project',
    demo: null,
    featured: true
  },
  {
    title: 'Shopee E-Commerce Tool',
    description: 'Automation tools for Shopee marketplace operations including product listing, price monitoring, and order management. Built with JavaScript and Shopee Open API.',
    tags: ['JavaScript', 'E-commerce', 'API', 'Automation'],
    github: 'https://github.com/kpmquockhanh/shopee-tool',
    demo: null,
    featured: true
  },
  {
    title: 'Simple Microservices (Go)',
    description: 'Microservices architecture demonstration built with Go. Features service discovery, inter-service communication, and containerized deployment with Docker.',
    tags: ['Go', 'Microservices', 'Docker', 'gRPC', 'REST'],
    github: 'https://github.com/kpmquockhanh/simple-microservice-go',
    demo: null,
    featured: false
  },
  {
    title: 'Todolist App',
    description: 'A clean and functional todo list application built with JavaScript. Features task management, categorization, and progress tracking.',
    tags: ['JavaScript', 'Web', 'Productivity', 'Frontend'],
    github: 'https://github.com/kpmquockhanh/Todolist-KHANHLQ',
    demo: null,
    featured: false
  },
  {
    title: 'Hanie English',
    description: 'Full-featured English learning platform built with Laravel. Features integrated REST APIs, Blade templating with reusable components, and dynamic content management for educational materials.',
    tags: ['PHP', 'Laravel', 'Blade', 'REST API', 'MySQL'],
    github: 'https://github.com/kpmquockhanh/hanie-english',
    demo: null,
    featured: false
  },
  {
    title: 'Sudoku Game',
    description: 'Interactive Sudoku puzzle game built with JavaScript demonstrating the backtracking algorithm for puzzle generation and solving. Features multiple difficulty levels, validation, and a clean user interface.',
    tags: ['JavaScript', 'Algorithm', 'Backtracking', 'Game', 'Puzzle'],
    github: 'https://github.com/kpmquockhanh/Sodoku',
    demo: null,
    featured: false
  }
]
</script>

<template>
  <section id="projects" class="py-20 sm:py-24 bg-white">
    <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <h2 class="text-3xl sm:text-4xl font-bold text-primary mb-4">Featured Projects</h2>
        <p class="text-secondary max-w-2xl mx-auto">
          A selection of projects showcasing backend architecture, frontend development, and infrastructure automation.
        </p>
      </div>
      
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        <div 
          v-for="project in projects" 
          :key="project.title"
          class="group bg-white rounded-xl border border-border overflow-hidden hover:shadow-lg transition-all duration-300 flex flex-col"
          :class="{ 'md:col-span-2 lg:col-span-1': project.featured }"
        >
          <div class="p-6 flex flex-col flex-grow">
            <div class="flex items-center justify-between mb-4">
              <div class="w-10 h-10 rounded-lg bg-accent-light flex items-center justify-center">
                <Code2 class="w-5 h-5 text-accent" />
              </div>
              <div class="flex gap-2">
                <a 
                  v-if="project.github" 
                  :href="project.github" 
                  target="_blank" 
                  rel="noopener"
                  class="p-2 text-secondary hover:text-primary transition-colors"
                  title="View on GitHub"
                >
                  <GitHubIcon class="w-5 h-5" />
                </a>
                <a 
                  v-if="project.demo" 
                  :href="project.demo" 
                  target="_blank" 
                  rel="noopener"
                  class="p-2 text-secondary hover:text-primary transition-colors"
                  title="Live Demo"
                >
                  <ExternalLink class="w-5 h-5" />
                </a>
              </div>
            </div>
            
            <h3 class="font-semibold text-primary text-lg mb-2">{{ project.title }}</h3>
            <p class="text-secondary text-sm leading-relaxed mb-4 flex-grow">{{ project.description }}</p>
            
            <div class="flex flex-wrap gap-2 mt-auto">
              <span 
                v-for="tag in project.tags" 
                :key="tag"
                class="text-xs font-medium px-2.5 py-1 rounded-full bg-muted text-secondary"
              >
                {{ tag }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
