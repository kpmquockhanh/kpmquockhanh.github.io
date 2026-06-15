<script setup>
import { GraduationCap, Calendar, MapPin } from '@lucide/vue'

const education = [
  {
    degree: "Master's degree, Information Technology",
    school: "King's Own Institute",
    location: 'Sydney, Australia',
    period: '2024 – 2026'
  },
  {
    degree: "Bachelor's degree, Computer Software Engineering",
    school: 'Hanoi University of Industry',
    location: 'Vietnam',
    period: '2015 – 2019'
  }
]
</script>

<template>
  <section id="education" class="py-20 sm:py-24 bg-white">
    <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <h2 class="text-3xl sm:text-4xl font-bold text-primary mb-4">Education</h2>
        <p class="text-secondary max-w-2xl mx-auto">
          Academic background in Computer Software Engineering and Master's degree from King's Own Institute, Sydney.
        </p>
      </div>
      
      <div class="space-y-6">
        <div 
          v-for="(edu, index) in education" 
          :key="index"
          class="bg-muted rounded-xl p-6 border border-border hover:shadow-md transition-shadow"
        >
          <div class="flex items-start gap-4">
            <div class="w-12 h-12 rounded-lg bg-accent-light flex items-center justify-center flex-shrink-0">
              <GraduationCap class="w-6 h-6 text-accent" />
            </div>
            <div class="flex-1">
              <h3 class="font-semibold text-primary text-lg">{{ edu.degree }}</h3>
              <p class="text-secondary font-medium">{{ edu.school }}</p>
              <div class="flex items-center gap-4 text-sm text-secondary/70 mt-2">
                <span class="flex items-center gap-1">
                  <MapPin class="w-4 h-4" />
                  {{ edu.location }}
                </span>
                <span class="flex items-center gap-1">
                  <Calendar class="w-4 h-4" />
                  {{ edu.period }}
                </span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
