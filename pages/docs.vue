<template>
  <div class="min-h-screen bg-gradient-to-br from-slate-800 via-slate-900 to-slate-950">
    <!-- Add this navigation menu -->
    <nav class="fixed top-24 right-8 hidden xl:block">
      <div class="bg-slate-800/80 backdrop-blur-sm rounded-xl p-4 border border-slate-700/50 w-48">
        <h3 class="text-lg font-semibold bg-gradient-to-r from-cyan-400 via-purple-500 to-violet-500 text-transparent bg-clip-text mb-4">
          Contents
        </h3>
        <ul class="space-y-2">
          <li v-for="(section, index) in sections" :key="index">
            <a 
              :href="`#${section.title.toLowerCase().replace(/\s+/g, '-')}`"
              class="text-gray-300 hover:text-cyan-400 transition-colors text-sm block py-1"
              @click="highlightSection(section.title.toLowerCase().replace(/\s+/g, '-'))"
            >
              {{ section.title }}
            </a>
          </li>
        </ul>
      </div>
    </nav>

    <div class="container mx-auto px-4">
      <div class="max-w-4xl mx-auto">
        <h1 class="text-4xl font-bold mb-8 bg-gradient-to-r from-cyan-400 via-purple-500 to-violet-500 text-transparent bg-clip-text">
          Documentation
        </h1>
        
        <div class="space-y-12">
          <section 
            v-for="(section, index) in sections" 
            :key="index" 
            :id="section.title.toLowerCase().replace(/\s+/g, '-')"
            class="bg-slate-800/80 backdrop-blur-sm rounded-xl shadow-lg hover:shadow-xl transition-shadow p-8 border border-slate-700/50 group scroll-mt-24"
          >
            <h2 class="text-2xl font-bold bg-gradient-to-r from-cyan-400 via-purple-500 to-violet-500 text-transparent bg-clip-text transition-transform">
              {{ section.title }}
            </h2>
            <p class="text-gray-300 mb-4">{{ section.description }}</p>
            <div v-if="section.code" class="relative bg-slate-950 p-4 rounded-lg border border-slate-700/50 group">
              <button 
                @click="copyToClipboard(section.code)"
                class="absolute top-2 right-2 text-gray-400 hover:text-cyan-400 transition-colors"
              >
                <Icon name="ph:copy" class="w-5 h-5" />
              </button>
              <pre class="text-sm block overflow-x-auto">
                <code v-for="line in section.code.split('\n')" :key="line" class="block">
                  <span v-if="line.startsWith('#')" class="text-violet-400">{{ line }}</span>
                  <span v-else class="text-cyan-400">{{ line }}</span>
                </code>
              </pre>
            </div>
          </section>
        </div>
        
        <div class="mt-12 text-center">
          <NuxtLink 
            to="/" 
            class="inline-flex items-center px-6 py-3 rounded-lg bg-gradient-to-r from-cyan-500 to-violet-500 text-white hover:from-cyan-600 hover:to-violet-600 transition-all mb-16 group"
          >
            <span class="mr-2 group-hover:-translate-x-1 transition-transform">←</span> Back to Home
          </NuxtLink>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
interface Section {
  title: string;
  description: string;
  code?: string;
}

const sections: Section[] = [
  {
    title: 'Getting Started',
    description: 'Start building your next project with this Nuxt 3 template. The template comes with TypeScript, Tailwind CSS, and modern development tools preconfigured.',
    code: '# Clone the repository\n$ git clone https://github.com/ls047/Nuxi-template.git\n\n# Navigate to project\n$ cd Nuxi-template\n\n# Install dependencies\n$ npm install'
  },
  {
    title: 'Project Structure',
    description: 'This template follows Nuxt 3 conventions with enhanced organization:\n\n• pages/ - All your page components\n• components/ - Reusable Vue components\n• layouts/ - Page layouts and templates\n• public/ - Static assets\n• composables/ - Reusable Vue composition functions'
  },
  {
    title: 'Development Workflow',
    description: 'The development server includes hot module replacement, auto-imports, and TypeScript checking. Use these commands for development:',
    code: '# Start development server\n$ npm run dev\n\n# Type checking\n$ npm run typecheck'
  },
  {
    title: 'Building for Production',
    description: 'Create an optimized production build with these steps. The build process includes automatic code splitting, minification, and optimized assets.',
    code: '# Create production build\n$ npm run build\n\n# Preview production build\n$ npm run preview'
  },
  {
    title: 'Features & Customization',
    description: 'Key features include:\n\n• Full TypeScript support with strict mode\n• Tailwind CSS with custom configuration\n• Auto-imported components and composables\n• SEO optimization ready\n• Modern development tools integration'
  },
  {
    title: 'Deployment',
    description: 'This template is compatible with various hosting platforms. The production build is optimized for performance and can be deployed to Vercel, Netlify, or any static hosting service.',
    code: '# Generate static site\n$ npm run generate\n\n# Deploy to your hosting platform\n$ npm run deploy'
  }
];
const copyToClipboard = (text: string) => {
  navigator.clipboard.writeText(text).then(() => {
    // You could add a toast notification here if desired
    console.log('Copied to clipboard');
  });
};
const highlightSection = (sectionId: string) => {
  const section = document.getElementById(sectionId);
  if (section) {
    section.classList.add('section-highlight');
    setTimeout(() => {
      section.classList.remove('section-highlight');
    }, 2000);
  }
};
</script>