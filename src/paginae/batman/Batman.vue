<script setup lang="ts">



import CarrusImaginum from '@/components/ui/CarrusImaginum.vue'
import { scrollToSection } from '@/utils/scrollToSection';
import { useMouseMotio } from '@/composables/useMouseMotion';
import { Navigation } from '@lucide/vue';
import NavigatorPrimarius from '@/components/NavigatorPrimarius.vue';
import { MenuItem } from 'reka-ui/internal';


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



const photos = ["justice", "arkham", "superman", "varios", "villana", "villano", "grupo", "robin", "anne", "joker", "resplandor", "cat", "gafas", "league", "fondoVerde"]; 

const { mousePositione, cumMouseMove, cumMouseLeave } = useMouseMotio()

const menuItems = [
 {
  label: 'Portada',
  href: '#',
  onClick: () => scrollToSection('#')
 }, 
 {
  label: 'Vehiculos',
  href: '#vehiculis',
  onClick: () => scrollToSection('#vehiculis')
 }, 
  {
  label: 'Imágenes',
  href: '#videre',
  onClick: () => scrollToSection('#videre')
 }, 
  {
  label: 'Contacto',
  href: '#contactus',
  onClick: () => scrollToSection('#contactus')
 }, 

] 

</script>

<template>
  <main>
    <div class="batman">

    <NavigatorPrimarius :items="menuItems" homeRoute="/" />

    <header id="titulus-batman" class="titulus">
      <h1>Batman</h1>
      <div class="titulus-img"
      @mousemove="cumMouseMove"
      @mouseleave="cumMouseLeave"
      :style="{
        backgroundPositionX: `calc(50% + ${mousePositione.x}px)`,
        backgroundPositionY: `calc(50% + ${mousePositione.y}px)`,
        transition: 'background-position 0.1s ease-out'
      }"
      ></div>
      <p>Él puede tomar las decisiones que nadie más puede, la decisión correcta</p>
    </header>


      <section id="vehiculis">
        <div class="vehiculis-arca">
          <div class="item unus">
              <div class="notitia">
                <h2>Avión</h2>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed vehicula vulputate elit eget fermentum. Ut laoreet ante lacus. Quisque ut tincidunt metus. Curabitur congue, arcu nec tempus sodales, neque sem ultrices mauris, eu tincidunt nibh nibh eu massa. Aenean rhoncus quis nibh ac facilisis.</p>
                <small>Fabricado en 2005</small>
              </div>
              <img src="/imagines/batman/avion.jpg"/>
            </div>

            <div class="item duo">
              <div class="notitia">
                <h2>Moto</h2>
                <p>Nulla aliquip cupidatat voluptate veniam nostrud aliquip sit enim officia. Sit eu pariatur officia qui dolor adipisicing cupidatat. Sit consectetur et eu ut esse laboris nulla.</p>
                <small>Fabricado en 2006</small>
              </div>
              <img src="/imagines/batman/moto.jpg"/>
            </div>
            
            <div class="item tribus">
              <div class="notitia">
                <h2>Coche</h2>
                <p>Irure adipisicing est minim eu ad dolor. Eu ea commodo pariatur ut occaecat in cupidatat reprehenderit ut laborum duis. Sunt minim ex fugiat reprehenderit. Lorem consectetur reprehenderit commodo non</p>
                <small>Fabricado en 2007</small>
              </div>
              <img src="/imagines/batman/car.jpg"/>
            </div>
          </div>

          <div class="vehiculis-titulus">
            <h1>Vehículos de Batman</h1>
          </div>
      </section>

      <section id="videre" class="flex w-full justify-center min-h[60hv] lg:min-h[95hv] items-center bg-gray-900">
         
        <CarrusImaginum
          :photos="photos"
          basePath="/imagines/batman"
          :autoplay-delay="1500"
          />

      </section>

    </div>
  </main>
</template>

<style scoped>
.batman {
  position: relative;
  min-height: 100vh;
  font-family: Arial, Helvetica, sans-serif;
}

.menu-toggle {
  display: none;
}

.extra-nav {
  position: fixed;
  inset: 0 0 auto;
  z-index: 10;
  box-sizing: border-box;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
  min-height: 4rem;
  padding: 0 1rem;
  background: rgba(255, 255, 255, 0.94);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.25);
}

.home-link {
  display: flex;
  align-items: center;
  color: slateblue;
}



.titulus {
  position: relative;
}

.titulus-img {
  aspect-ratio: 8/7;
  background-image: url("../imagines/batman/batman.jpg");
  background-position: center center;
  background-size: 100% 100%;
}

.titulus > h1 {
  position: absolute;
  top: calc(100vw * 0.5);
  width: 100%;
  margin: 0;
  color: white;
  font-family: batman, Arial, sans-serif;
  font-size: 5rem;
  text-align: center;
  pointer-events: none;
}

.titulus > p {
  position: absolute;
  top: calc(100vw * 0.25);
  width: 100%;
  color: white;
  font-family: batman, Arial, sans-serif;
  font-size: 2rem;
  text-align: center;
  pointer-events: none;
  display: none;
}

.page-section {
  min-height: 70vh;
  padding: 6rem 2rem 2rem;
  scroll-margin-top: 4rem;
  background: #f4f4f7;
  color: #151934;
}

.page-section:nth-of-type(odd) {
  background: #e6e8f0;
}

.page-section h2 {
  margin: 0;
  font-size: 2rem;
}

@media (max-width: 639px) {
  .menu-toggle {
    position: absolute;
    inset: 0 0 auto;
    z-index: 20;
    display: flex;
    align-items: center;
    justify-content: flex-start;
    width: 100%;
    height: 2.75rem;
    padding: 0 1rem;
    border: 0;
    border-radius: 0;
    background: #fff;
    color: #222;
    cursor: pointer;
  }

  .extra-nav {
    display: none;
    position: absolute;
    inset: 2.75rem auto auto 0;
    align-items: flex-start;
    justify-content: flex-start;
    gap: 0.25rem;
    width: 11rem;
    min-height: 0;
    padding: 0.5rem;
    border-radius: 0 0 1rem 0;
    background: rgba(255, 255, 255, 0.82);
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.25);
  }

  .extra-nav.is-open {
    display: flex;
  }
}

@media (min-width: 768px) {
  .titulus > p {
    display: block;
  }
}

#vehiculis {
  max-width: 510px;
  margin: 0 auto;
  padding: 4rem 0;
  display: flex;
  flex-direction: column;
}

.vehiculis-arca {
  order: 1;
  display: flex;
  flex-direction: column;
}

.vehiculis-titulus {
  height: 5.5rem; /* 88px */
  font-size: 2rem;
  background-color: rgba(0, 0, 0, 0.7);
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
}

.item {
  padding: 1.5rem 0;
  height: 540px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
}

.item > img {
  width: 450px;
}

.unus {
  background-color: rgba(220, 220, 220, 0.2) ; 
  order: 2;
}

.duo {
  background-color: rgba(220, 220, 220, 0.8);
}

.tribus {
  background-color: rgba(220, 220, 220, 0.8);
  order: 3;
}

.notitia {
  width: 90%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
 
.notitia > small {
  font-weight: bold;
  padding: 1rem;
}
 
.notitia > h2 {
 font-size: 1.7rem; 
 font-weight: 600;
 color: rgba(0, 0, 0, 0.7);
 padding-bottom: 1rem;
} 


@media (min-width: 640px) {
  #vehiculis {
    max-width: 576px;
  }
}

  @media (min-width: 768px) {
    #vehiculis {
      max-width: 900px;
  }

  .item {
    flex-direction: row;
    height: 320px;
  }

  .notitia {
    width: 40%;
  }

  .unus > img {
    order: -1;
  }

  @media (min-width: 1024px) {
    #vehiculis {
      max-width: 1280px;
      }
  }

  .item {
    flex-direction: column;
    height: 560px;
  }


  .vehiculis-arca {
    flex-direction: row;

  }

  .notitia {
    width: 90%;
  }

}
</style>
