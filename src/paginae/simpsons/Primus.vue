<script setup lang="ts">
import { Button } from '@/components/ui/button'
import LogoSimpsons from '@/components/ui/LogoSimpsons.vue'
</script>

<template>
  <div class="bg-simpsons-yellow min-h-screen text-center p-4 flex flex-col items-center justify-center">
   
    <LogoSimpsons estilus="w-[26rem] max-w-[90vw] h-auto" />
   
   
    <h1 class="text-xl my-1 font-medium">
      Discover some of the most amazing Quotes from The Simpsons
    </h1>
    <div>
      <strong>This is an unofficial app (even though it looks so cool!)</strong>
    </div>
    <div class="mt-8 flex gap-5">
      <Button as-child variant="tertiarius" size="elongatis">
        <RouterLink to="/">Exit</RouterLink>
      </Button>
      <Button as-child variant="tertiarius" size="elongatis">
        <RouterLink to="/simpsons/about">Enter</RouterLink>
      </Button>
    </div>

    <div class="flex gap-12">
      <img class="object-contain hidden sm:block" src="/imagines/simpsons/bart.png" width="200px">
      <img class="object-contain mt-20 hidden sm:block" src="/imagines/simpsons/homer.png" width="195px">
      <img class="object-contain mt-12 md:mt-0" src="/imagines/simpsons/moe.png" width="220px">
    </div> 

  </div>
</template>



