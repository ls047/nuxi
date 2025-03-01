<template>
  <div class="min-h-screen bg-gradient-to-br from-slate-800 via-slate-900 to-slate-950">
    <div class="container mx-auto px-4 py-8 md:py-16">
      <div class="text-center mb-8 md:mb-16 pt-16">
        <h1 class="text-4xl md:text-6xl font-bold mb-4 bg-gradient-to-r from-cyan-400 via-purple-500 to-violet-500 text-transparent bg-clip-text animate-gradient bg-300">
          Nuxt 3 Template
        </h1>
        <p class="text-lg md:text-xl text-gray-300 max-w-2xl mx-auto px-4">
          A modern, TypeScript-ready template with built-in Tailwind CSS and best practices
        </p>
      </div>
      
      <!-- Feature cards are already updated via FeatureCard component -->
      
      <div class="bg-slate-800/80 rounded-xl md:rounded-2xl shadow-xl p-6 md:p-10 mb-8 md:mb-16 backdrop-blur-sm border border-slate-700/50">
        <h2 class="text-3xl font-bold mb-8 bg-gradient-to-r from-cyan-400 via-purple-500 to-violet-500 text-transparent bg-clip-text">
          Quick Start Guide
        </h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-12">
          <div class="space-y-6">
            <h3 class="text-2xl font-semibold text-gray-200">Project Features</h3>
            <ul class="space-y-4 text-gray-300">
              <li class="flex items-center">
                <span class="mr-3 text-cyan-400">
                  <Icon name="ph:check-circle-fill" class="w-5 h-5" />
                </span>
                TypeScript Support
              </li>
              <li class="flex items-center">
                <span class="mr-3 text-cyan-400">
                  <Icon name="ph:check-circle-fill" class="w-5 h-5" />
                </span>
                Tailwind CSS with Custom Config
              </li>
              <li class="flex items-center">
                <span class="mr-3 text-cyan-400">
                  <Icon name="ph:check-circle-fill" class="w-5 h-5" />
                </span>
                Auto-imported Components
              </li>
              <li class="flex items-center">
                <span class="mr-3 text-cyan-400">
                  <Icon name="ph:check-circle-fill" class="w-5 h-5" />
                </span>
                SEO Optimization
              </li>
            </ul>
          </div>
          <div class="space-y-6">
            <h3 class="text-2xl font-semibold text-gray-200">Getting Started</h3>
            <div class="bg-slate-950 p-6 rounded-xl border border-slate-700/50">
              <code class="text-sm block">
                <span class="text-violet-400"># Install dependencies</span><br/>
                <span class="text-cyan-400">npm install</span><br/><br/>
                <span class="text-violet-400"># Start development server</span><br/>
                <span class="text-cyan-400">npm run dev</span>
              </code>
            </div>
          </div>
        </div>
      </div>
      <!-- Add this contact section before closing div -->
      <div class="mt-12 md:mt-24 bg-slate-800/80 rounded-xl md:rounded-2xl shadow-xl p-8 md:p-16 backdrop-blur-sm border border-slate-700/50">
        <h2 class="text-2xl md:text-3xl font-bold text-center bg-gradient-to-r from-cyan-400 to-violet-400 text-transparent bg-clip-text mb-8">
          Connect With Me
        </h2>
        <div class="flex flex-col md:flex-row justify-center items-center space-y-6 md:space-y-0 md:space-x-8">
          <a 
            href="https://github.com/ls047" 
            target="_blank"
            class="group flex items-center space-x-3 text-gray-300 hover:text-cyan-400 transition-colors w-full md:w-auto justify-center"
          >
            <Icon name="mdi:github" class="w-6 h-6 md:w-8 md:h-8" />
            <span class="group-hover:translate-x-1 transition-transform">GitHub</span>
          </a>
          <a 
            href="https://www.linkedin.com/in/ali-alibadi-33b303286/" 
            target="_blank"
            class="group flex items-center space-x-3 text-gray-300 hover:text-cyan-400 transition-colors w-full md:w-auto justify-center"
          >
            <Icon name="mdi:linkedin" class="w-6 h-6 md:w-8 md:h-8" />
            <span class="group-hover:translate-x-1 transition-transform">LinkedIn</span>
          </a>
          <a 
            href="https://www.instagram.com/ls047_/" 
            target="_blank"
            class="group flex items-center space-x-3 text-gray-300 hover:text-cyan-400 transition-colors w-full md:w-auto justify-center"
          >
            <Icon name="mdi:instagram" class="w-6 h-6 md:w-8 md:h-8" />
            <span class="group-hover:translate-x-1 transition-transform">Instagram</span>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.animate-gradient {
  background-size: 300%;
  -webkit-animation: animatedgradient 6s ease infinite alternate;
  animation: animatedgradient 6s ease infinite alternate;
}

.bg-300 {
  background-size: 300%;
}

@keyframes animatedgradient {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}
</style>
<script setup lang="ts">
interface Feature {
  title: string;
  description: string;
  icon: string;
}

const features: Feature[] = [
  {
    title: 'TypeScript Ready',
    description: 'Full TypeScript support with enhanced type checking and IDE integration for a better development experience.',
    icon: '⚡'
  },
  {
    title: 'Modern Styling',
    description: 'Tailwind CSS integration with custom configurations and modern design patterns.',
    icon: '🎨'
  },
  {
    title: 'Best Practices',
    description: 'Built following Vue.js and Nuxt.js best practices with optimized performance.',
    icon: '✨'
  }
];
</script>