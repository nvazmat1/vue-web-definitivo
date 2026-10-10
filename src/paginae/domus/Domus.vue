<script setup lang="ts">
import { Button } from '@/components/ui/button'

</script>

<template>

  <div class="fondo-home">

      <h1>
        <span>Diseño</span> Web y
        <br>
        Apps <span>Interactivas</span>

        
      </h1>

    <div class="botones">

      <Button as-child>
         <RouterLink to="/indecision">Sí o no</RouterLink>
       </Button>
     
       <Button as-child variant="destructive">
         <RouterLink to="/batman">Batman</RouterLink>
        </Button>

       <Button as-child variant="destructive">
         <RouterLink to="/simpsons">Simpsons</RouterLink>
       </Button>

       <Button as-child variant="destructive">
         <a href="https://www.upv.es">UPV</a>
       </Button>

    </div>
  </div>
</template>



<style scoped>
.fondo-home {
  background-color: rgb(21, 25, 52);
  height: 100vh;
  color: rgb(24, 182, 246);

}

.botones {
  display: flex;
  gap: 0.5rem;
}

.botones > a {
  background-color: rgb(24, 182, 246);
  margin-right: 0.5rem;
}

.botones > a:hover {
  background-color: rgba(24, 182, 246, 0.7);
}
</style>