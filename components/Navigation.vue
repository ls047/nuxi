<template>
  <nav class="fixed w-full z-50 bg-slate-900/80 backdrop-blur-md border-b border-slate-700/50">
    <div class="container mx-auto px-6 py-4">
      <div class="flex items-center justify-between">
        <NuxtLink to="/" class="text-xl md:text-2xl font-bold bg-gradient-to-r from-cyan-400 via-purple-500 to-violet-500 text-transparent bg-clip-text">
          Nuxt Template
        </NuxtLink>
        
        <!-- Mobile Menu Button -->
        <button @click="isOpen = !isOpen" class="block md:hidden text-gray-300">
          <Icon :name="isOpen ? 'ph:x-bold' : 'ph:list-bold'" class="w-6 h-6" />
        </button>

        <!-- Desktop Menu -->
        <div class="hidden md:flex items-center space-x-8">
          <NuxtLink 
            v-for="link in navLinks" 
            :key="link.path" 
            :to="link.path"
            class="text-gray-300 hover:text-cyan-400 transition-colors"
          >
            {{ link.name }}
          </NuxtLink>
        </div>
      </div>

      <!-- Mobile Menu -->
      <transition
        enter-active-class="transition duration-200 ease-out"
        enter-from-class="transform -translate-y-4 opacity-0"
        enter-to-class="transform translate-y-0 opacity-100"
        leave-active-class="transition duration-150 ease-in"
        leave-from-class="transform translate-y-0 opacity-100"
        leave-to-class="transform -translate-y-4 opacity-0"
      >
        <div 
          v-show="isOpen" 
          class="md:hidden absolute left-0 right-0 top-full bg-slate-900/95 backdrop-blur-md border-b border-slate-700/50"
        >
          <div class="container mx-auto px-6 py-4">
            <NuxtLink 
              v-for="link in navLinks" 
              :key="link.path" 
              :to="link.path"
              class="block text-gray-300 hover:text-cyan-400 transition-colors py-2"
              @click="isOpen = false"
            >
              {{ link.name }}
            </NuxtLink>
          </div>
        </div>
      </transition>
    </div>
  </nav>
  <!-- Add spacing div to prevent content overlap -->
  <div class="h-20"></div>
</template>

<script setup>
const isOpen = ref(false)

const navLinks = [
  { name: 'Home', path: '/' },
  { name: 'Documentation', path: '/docs' }
];
</script>