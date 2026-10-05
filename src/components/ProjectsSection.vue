<script setup lang="ts">
interface Project {
  title: string
  description: string
  technologies: string[]
  metrics: string
  link?: string
  descriptionLink?: string
}

const projects: Project[] = [
  {
    title: 'Forecasting NYC 311 Call Volume',
    description: 'Designed and implemented a real-time data processing pipeline using Apache Kafka and Apache Spark Streaming, processing over 1M events per minute.',
    technologies: ['Python', 'DuckDB', 'AWS', 'Python'],
    metrics: 'Reduced data processing latency by 60%',
    link: 'https://nyc311-pipeline.onrender.com/',
    descriptionLink: 'https://app.notion.com/p/NYC-311-Dashboard-Deployment-Runbook-3cd98a4d6a52802d8d4adbd2b0b85946?source=copy_link'
  },
  {
    title: 'Call Volume Forecasting with R',
    description: 'Developed an interactive NYC 311 Forecasting Application for Operational Analytics',
    technologies: ['R', 'Docker', 'R Shiny,', 'DuckDB'],
    metrics: 'Improved query performance by 80%',
    link: 'https://nyc311-shiny.onrender.com/',
    descriptionLink: 'https://github.com/AdurojaSamuel/nyc311_pipeline.git'
  },
  {
    title: 'NYC 311 Operations Dashboard',
    description: 'Designed NYC 311 Analytics Dashboard for Monitoring Complaint for all New York City Borough',
    technologies: ['Python', 'SQL', 'DuckDB', 'PowerBI'],
    metrics: 'Reduced ~5hour PowerBI refresh to ~8-12mins',
    link: 'https://app.powerbi.com/view?r=eyJrIjoiNDQ1ZTBkZjMtZjA1OC00YjRhLTliZDYtMWM4YTQzZTViNmIzIiwidCI6IjVkMTYwOTRhLWNjMjEtNGFjMS1iYzAxLWFlOGZkNDBjOTRkMSJ9&pageName=p1_executive_overview',
    descriptionLink: 'https://app.notion.com/p/NYC311-PowerBI_DuckDB_Notion_Post-d0498a4d6a5282c8a89581fb1e5b8ea6?source=copy_link'
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
            <a
              v-if="project.descriptionLink"
              :href="project.descriptionLink"
              target="_blank"
              rel="noopener noreferrer"
              class="ml-1 text-primary-600 hover:underline"
            >
              Read more
            </a>
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