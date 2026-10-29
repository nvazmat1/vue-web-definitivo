<script setup lang="ts">
import { Button } from '@/components/ui/button'
import LogoSimpsons from '@/components/ui/LogoSimpsons.vue'
</script>

<template>
  <div class="flex min-h-screen flex-col">
    <header class="bg-simpsons-yellow w-full border border-black">
      <div class="flex flex-col md:flex-row w-full items-center justify-between p-3 mx-auto max-w-page md:px-20">
        <LogoSimpsons estilus="w-24 h-auto" />

        <nav class="flex items-center gap-5 text-sm">
          <RouterLink to="/simpsons/gallery" active-class="font-bold">
            Characters
          </RouterLink>
          <RouterLink to="/simpsons/about" active-class="font-bold">
            About
          </RouterLink>
          <Button
            as-child
            variant="tertiarius"
            size="elongatis"
            class="border border-black bg-simpsons-red px-3 hover:bg-simpsons-yellow focus:bg-simpsons-red"
          >
            <RouterLink to="/">Exit</RouterLink>
          </Button>
        </nav>
      </div>
    </header>

    <main class="flex-1 bg-white">
      <RouterView />
    </main>

    <footer class="bg-simpsons-yellow text-center py-6 w-full border border-black">
        <div>
            <strong>All Rights Reserved</strong> - Oh Lord Matt Groening - 1989-2027
        </div>

        <small>
            This app was done by Fernando Cordón
        </small>
    </footer>
  </div>
</template>
