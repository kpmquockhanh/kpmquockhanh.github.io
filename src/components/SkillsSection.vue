<script setup>
import { 
  Server, 
  Database, 
  Cloud, 
  Code2, 
  Container, 
  Boxes,
  Globe,
  HardDrive
} from '@lucide/vue'

const skills = [
  {
    category: 'Backend Development',
    icon: Server,
    items: [
      { name: 'Go (Golang)', level: 'Expert' },
      { name: 'PHP (Laravel)', level: 'Advanced' },
      { name: 'Node.js', level: 'Advanced' },
      { name: 'REST APIs', level: 'Advanced' },
      { name: 'Microservices', level: 'Advanced' },
      { name: 'TypeScript', level: 'Intermediate' }
    ]
  },
  {
    category: 'Frontend Development',
    icon: Code2,
    items: [
      { name: 'Vue.js', level: 'Expert' },
      { name: 'JavaScript', level: 'Expert' },
      { name: 'HTML/CSS', level: 'Expert' },
      { name: 'Tailwind CSS', level: 'Advanced' },
      { name: 'React Native', level: 'Intermediate' }
    ]
  },
  {
    category: 'Database & Storage',
    icon: Database,
    items: [
      { name: 'MySQL', level: 'Expert' },
      { name: 'NoSQL (MongoDB)', level: 'Advanced' },
      { name: 'Query Optimization', level: 'Advanced' },
      { name: 'Database Design', level: 'Advanced' },
      { name: 'Redis', level: 'Intermediate' }
    ]
  },
  {
    category: 'Cloud & Infrastructure',
    icon: Cloud,
    items: [
      { name: 'Docker', level: 'Expert' },
      { name: 'AWS', level: 'Advanced' },
      { name: 'Kubernetes', level: 'Advanced' },
      { name: 'Command Line', level: 'Expert' },
      { name: 'Linux', level: 'Advanced' }
    ]
  },
  {
    category: 'DevOps & Tools',
    icon: Container,
    items: [
      { name: 'Git & GitHub', level: 'Expert' },
      { name: 'CI/CD', level: 'Advanced' },
      { name: 'VPS Management', level: 'Advanced' },
      { name: 'Automation', level: 'Advanced' }
    ]
  },
  {
    category: 'Other Skills',
    icon: Boxes,
    items: [
      { name: 'Problem Solving', level: 'Advanced' },
      { name: 'Attention to Detail', level: 'Advanced' },
      { name: 'System Architecture', level: 'Advanced' },
      { name: 'Agile/Scrum', level: 'Intermediate' },
      { name: 'IELTS', level: 'Advanced' }
    ]
  }
]
</script>

<template>
  <section id="skills" class="py-20 sm:py-24 bg-muted">
    <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <h2 class="text-3xl sm:text-4xl font-bold text-primary mb-4">Skills & Technologies</h2>
        <p class="text-secondary max-w-2xl mx-auto">
          A comprehensive toolkit built over years of developing robust, scalable applications and infrastructure.
        </p>
      </div>
      
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        <div 
          v-for="skill in skills" 
          :key="skill.category"
          class="bg-white rounded-xl p-6 border border-border hover:shadow-lg transition-shadow"
        >
          <div class="flex items-center gap-3 mb-4">
            <div class="w-10 h-10 rounded-lg bg-accent-light flex items-center justify-center">
              <component :is="skill.icon" class="w-5 h-5 text-accent" />
            </div>
            <h3 class="font-semibold text-primary">{{ skill.category }}</h3>
          </div>
          <ul class="space-y-3">
            <li 
              v-for="item in skill.items" 
              :key="item.name"
              class="flex justify-between items-center text-sm"
            >
              <span class="text-secondary">{{ item.name }}</span>
              <span class="text-xs font-medium px-2 py-1 rounded-full bg-muted text-secondary">
                {{ item.level }}
              </span>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>
