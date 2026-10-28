
<script setup lang="ts">

import { House, Menu } from '@lucide/vue'
import {
  NavigationMenu,
  NavigationMenuItem,
  NavigationMenuLink,
  NavigationMenuList,
  navigationMenuTriggerStyle,
} from '@/components/ui/navigation-menu'
import { onMounted, onUnmounted, ref } from 'vue';


interface MenuItems { 
  label: string
  href: string
  onClick?: () => void
}

interface Props {
  items: MenuItems[]
  homeRoute?: string
}

withDefaults(defineProps<Props>(), {
  homeRoute: '/',
})


const videreMenu = ref<boolean>(true)

const handleResize = () => {
  if (window.innerWidth < 640) {
    videreMenu.value = false
  } else {
    videreMenu.value = true
  }
}

onMounted(() => {
  handleResize()
  window.addEventListener('resize', handleResize)
})

onUnmounted(() => {
  window.removeEventListener('resize', handleResize)
})

</script>

<template>
    <div>
    <Toggle class="fixed top-2 right-4 z-50 bg-slate-500 sm:hidden"
      @click="videreMenu = !videreMenu"
      >
      <Menu :size="46" />

    </Toggle>


    <nav v-if="videreMenu" :class="['extra-nav flex flex-col sm:flex-row', { 'is-open': videreMenu }]" aria-label="Navegación de Batman">
      <RouterLink class="home-link" to="/" aria-label="Volver a portada">
        <House class="icon-home" />
      </RouterLink>

      <NavigationMenu class="w-full max-w-none flex-none justify-start" :viewport="false">
        <NavigationMenuList class="flex w-full flex-col items-stretch justify-start sm:w-auto sm:flex-row">
          <NavigationMenuItem v-for="item in items" :key="item.label">
            <NavigationMenuLink as-child :class="[navigationMenuTriggerStyle(), 'text-md hover:bg-brand-purple hover:text-white transition-colors']">
              <a
                :href="item.href"
                @click.prevent="item.onClick ? item.onClick() : null"
              >
                {{ item.label }}
              </a>
            </NavigationMenuLink>
          </NavigationMenuItem>
        </NavigationMenuList>
      </NavigationMenu>
    </nav>
    </div>
</template>

<style scoped>

.icon-home {
  color: slateblue;
  width: 3rem;
  height: 3rem;
}

.icon-home:hover {
  color: white;
  background-color: slateblue;
}

.extra-nav {
  background-color: white;
  opacity: 0.7;
  box-shadow: rgba(0, 0, 0, 0.7);
  position: fixed;
  top: 0;
  z-index: 10;
}

@media (min-width: 640px) {
  .extra-nav {
    width: 100%;
    border-radius: 0%;
    opacity: 1;
    left: 0;
  }
}

</style>