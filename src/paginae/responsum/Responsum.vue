<template>
  <!--<h1>Indecision Page</h1> -->

  <RouterLink to="/" class="text-2xl ml-4">Home</RouterLink>


  <div class="w-[min(540px,90vw)] h-[min(540px,90vw)] border-2 m-3 grid grid-cols-4 grid-rows-3 gap-3">
    <div class="bg-sky-500 col-span-3 p-3 flex flex-row-reverse items-end gap-3">
      <div class="bg-sky-200 w-12 h-full"></div>
      <div class="bg-white w-12 h-[60%] order-first"></div>
      <div class="bg-sky-200 w-12 h-[30%]"></div>
      <div class="bg-sky-800 w-12 h-full flex-1"></div>
    </div>

    <div class="bg-pink-500 row-span-3 p-3 flex flex-col justify-between items-center">
      <div class="bg-pink-200 w-[80%] h-12"></div>
      <div class="bg-pink-200 w-full h-[60%] p-3 grid grid-cols-2 grid-rows-3 gap-3">
        <div class="bg-pink-500 row-span-2"></div>
        <div class="bg-white"></div>
        <div class="bg-white"></div>
        <div class="bg-pink-500 col-span-2"></div>
      </div>
      <div class="bg-pink-200 w-[40%] h-12 self-end"></div>
    </div>


     <div class="bg-lime-500 row-span-2 p-3 flex flex-col-reverse flex-wrap gap-3">
      <div class="bg-lime-200 w-8 h-[20%]"></div>
      <div class="bg-lime-200 w-8 h-[20%]"></div>
      <div class="bg-white w-8 h-[20%] order-first"></div>
      <div class="bg-lime-200 w-8 h-[20%]"></div>
      <div class="bg-white w-8 h-[20%] order-first"></div>
      <div class="bg-lime-200 w-8 h-[20%]"></div>

     </div>


     <div class="bg-amber-400 col-span-2 p-3 grid grid-cols-3 grid-rows-2 gap-2">
        <div class="bg-amber-100 col-span-2"></div>
        <div class="bg-white row-span-2"></div>
        <div class="bg-amber-100"></div>
        <div class="bg-amber-100"></div>
      </div>


     <div class="bg-violet-500 flex justify-center items-center">
        <div class="bg-violet-200 w-16 h-16 rounded-full"></div>

     </div>

      <div class="bg-teal-500 p-2 grid grid-cols-3 gap-2 content-center">
        <div class="bg-teal-200 w-7 h-7"></div>
        <div class="bg-teal-200 w-7 h-7"></div>
        <div class="bg-teal-200 w-7 h-7"></div>
        <div class="bg-teal-200 w-7 h-7"></div>
        <div class="bg-teal-200 w-7 h-7"></div>
      </div>

   </div>
</template>
