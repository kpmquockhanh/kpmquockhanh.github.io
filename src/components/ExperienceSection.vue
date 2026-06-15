<script setup>
import { Calendar, MapPin, Building2 } from '@lucide/vue'

const experiences = [
  {
    title: 'Full Stack Engineer',
    company: 'OpenCommerce Group',
    location: 'Hanoi, Vietnam',
    period: 'Oct 2020 - Feb 2024',
    description: 'Worked on a large and complex ecommerce system with microservices architecture. Developed backend services using Go and PHP (Laravel), built frontend interfaces with Vue.js, and managed databases including MySQL and non-SQL solutions. Handled cloud infrastructure, Docker containers, and Kubernetes clusters.',
    technologies: ['Go', 'PHP (Laravel)', 'Vue.js', 'Node.js', 'MySQL', 'MongoDB', 'Docker', 'Kubernetes', 'AWS', 'Microservices']
  },
  {
    title: 'Developer',
    company: 'HBLAB Joint Stock Company',
    location: 'Vietnam',
    period: 'Dec 2018 - Oct 2020',
    description: 'Developed and maintained web applications using modern technologies. Worked with MySQL databases and contributed to full-stack development projects.',
    technologies: ['PHP', 'MySQL', 'Vue.js', 'JavaScript', 'HTML/CSS', 'REST APIs']
  },
  {
    title: 'Web Developer',
    company: 'VNP Group',
    location: 'Vietnam',
    period: 'Jan 2018 - Jul 2018',
    description: 'Part-time web development role building and maintaining web applications. Gained practical experience in full-stack development and database management.',
    technologies: ['PHP', 'MySQL', 'JavaScript', 'HTML/CSS', 'jQuery']
  }
]
</script>

<template>
  <section id="experience" class="py-20 sm:py-24 bg-muted">
    <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <h2 class="text-3xl sm:text-4xl font-bold text-primary mb-4">Work Experience</h2>
        <p class="text-secondary max-w-2xl mx-auto">
          Professional journey spanning backend development, infrastructure management, and full-stack application delivery.
        </p>
      </div>
      
      <div class="relative">
        <!-- Timeline line -->
        <div class="absolute left-4 sm:left-8 top-0 bottom-0 w-px bg-border"></div>
        
        <div class="space-y-8">
          <div 
            v-for="(exp, index) in experiences" 
            :key="index"
            class="relative pl-12 sm:pl-20"
          >
            <!-- Timeline dot -->
            <div class="absolute left-2 sm:left-6 top-2 w-4 h-4 rounded-full bg-accent border-4 border-white shadow-sm"></div>
            
            <div class="bg-white rounded-xl p-6 border border-border hover:shadow-md transition-shadow">
              <div class="flex flex-wrap items-start justify-between gap-2 mb-3">
                <div>
                  <h3 class="font-semibold text-primary text-lg">{{ exp.title }}</h3>
                  <div class="flex items-center gap-4 text-sm text-secondary mt-1">
                    <span class="flex items-center gap-1">
                      <Building2 class="w-4 h-4" />
                      {{ exp.company }}
                    </span>
                    <span class="flex items-center gap-1">
                      <MapPin class="w-4 h-4" />
                      {{ exp.location }}
                    </span>
                  </div>
                </div>
                <span class="flex items-center gap-1 text-sm font-medium text-accent bg-accent-light px-3 py-1 rounded-full">
                  <Calendar class="w-4 h-4" />
                  {{ exp.period }}
                </span>
              </div>
              
              <p class="text-secondary text-sm leading-relaxed mb-4">{{ exp.description }}</p>
              
              <div class="flex flex-wrap gap-2">
                <span 
                  v-for="tech in exp.technologies" 
                  :key="tech"
                  class="text-xs font-medium px-2.5 py-1 rounded-full bg-muted text-secondary"
                >
                  {{ tech }}
                </span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
