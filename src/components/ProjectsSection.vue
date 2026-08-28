<script setup lang="ts">
interface Project {
  title: string
  description: string
  technologies: string[]
  metrics: string
  link?: string
}

const projects: Project[] = [
  {
    title: 'Real-time Analytics Pipeline',
    description: 'Designed and implemented a real-time data processing pipeline using Apache Kafka and Apache Spark Streaming, processing over 1M events per minute.',
    technologies: ['Python', 'DuckDB', 'AWS', 'Python'],
    metrics: 'Reduced data processing latency by 60%',
    link: 'https://nyc311-pipeline.onrender.com/'
  },
  {
    title: 'Data Warehouse Migration',
    description: 'Led the migration of an on-premise data warehouse to Snowflake, implementing modern data modeling practices using dbt.',
    technologies: ['R', 'Docker', 'Python', 'Airflow'],
    metrics: 'Improved query performance by 80%',
    link: 'https://nyc311-shiny.onrender.com/'
  },
  {
    title: 'ML Feature Pipeline',
    description: 'Built an automated feature engineering pipeline for machine learning models, handling both batch and streaming data sources.',
    technologies: ['Python', 'Spark', 'Feature Store', 'MLflow'],
    metrics: 'Reduced feature computation time by 70%',
    link: 'https://nyc311-data-viz.shinyapps.io/app311/'
  }
]
</script>

<template>
  <section id="projects" class="py-20 bg-white dark:bg-gray-800">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <h2 class="section-title">Featured Projects</h2>
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="(project, index) in projects" :key="index" 
          class="card hover:translate-y-[-4px] transition-transform">
          <h3 class="text-xl font-semibold mb-3">
            <a
              v-if="project.link"
              :href="project.link"
              target="_blank"
              rel="noopener noreferrer"
              class="hover:text-primary-600 transition-colors"
            >
              {{ project.title }}
            </a>
            <span v-else>{{ project.title }}</span>
          </h3>
          <p class="text-gray-600 dark:text-gray-300 mb-4">
            {{ project.description }}
          </p>
          <div class="flex flex-wrap gap-2 mb-4">
            <span v-for="tech in project.technologies" :key="tech"
              class="px-2 py-1 bg-gray-100 dark:bg-gray-700 rounded text-sm">
              {{ tech }}
            </span>
          </div>
          <p class="text-primary-600 font-medium">
            {{ project.metrics }}
          </p>
        </div>
      </div>
    </div>
  </section>
</template>