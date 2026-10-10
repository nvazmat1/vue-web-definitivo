<script setup lang="ts">
import { House } from '@lucide/vue'
import {
  NavigationMenu,
  NavigationMenuItem,
  NavigationMenuLink,
  NavigationMenuList,
  navigationMenuTriggerStyle,
} from '@/components/ui/navigation-menu'

const scrollToSection = (sectionId) => {

  if (sectionId === "#") {
    window.scrollTo({ top: 0, behavior: 'smooth' });
    return
  }

  const element = document.querySelector<HTMLElement>(sectionId);

    if (element) {
      element.scrollIntoView({ behavior: 'smooth', block: 'start' });
    }

  //const id = sectionId.replace(/^#/, '')

  //if (!id) {
    //window.scrollTo({ top: 0, behavior: 'smooth' })
    //return
  //}

  //document.getElementById(id)?.scrollIntoView({
    //behavior: 'smooth',
    //block: 'start',
  //})
}
</script>

<template>
  <main class="batman">
    <nav class="extra-nav" aria-label="Navegación de Batman">
      <RouterLink class="home-link" to="/" aria-label="Volver a portada">
        <House class="icon-home" />
      </RouterLink>

      <NavigationMenu :viewport="false">
        <NavigationMenuList>
          <NavigationMenuItem>
            <NavigationMenuLink as-child :class="navigationMenuTriggerStyle()">
              <a href="#vehiculis" @click.prevent="scrollToSection('#vehiculis')">
                Vehículos
              </a>
            </NavigationMenuLink>
          </NavigationMenuItem>

          <NavigationMenuItem>
            <NavigationMenuLink as-child :class="navigationMenuTriggerStyle()">
              <a href="#videre" @click.prevent="scrollToSection('#videre')">
                Imágenes
              </a>
            </NavigationMenuLink>
          </NavigationMenuItem>

          <NavigationMenuItem>
            <NavigationMenuLink as-child :class="navigationMenuTriggerStyle()">
              <a href="#contactus" @click.prevent="scrollToSection('#contactus')">
                Contacto
              </a>
            </NavigationMenuLink>
          </NavigationMenuItem>
        </NavigationMenuList>
      </NavigationMenu>
    </nav>

    <header id="portada-batman" class="titulus">
      <h1>Batman</h1>
      <div class="titulus-img"></div>
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





    <section id="videre" class="page-section">
      <h2>Imágenes</h2>
    </section>

    <section id="contactus" class="page-section">
      <h2>Contacto</h2>
    </section>
  </main>
</template>

<style scoped>
.batman {
  min-height: 100vh;
  font-family: Arial, Helvetica, sans-serif;
}

.extra-nav {
  position: fixed;
  inset: 0 0 auto;
  z-index: 10;
  box-sizing: border-box;
  display: flex;
  align-items: center;
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

.icon-home {
  width: 1.75rem;
  height: 1.75rem;
}

.titulus-img {
  min-height: 100vh;
  background-color: #151934;
  background-image: url("../imagines/batman/batman.jpg");
  background-position: center;
  background-size: cover;
}

.titulus > h1 {
  position: absolute;
  top: 63%;
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
  top: 36%;
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

@media (min-width: 768px) {
  .titulus > p {
    display: block;
  }
}

#vehiculis {
  max-width: 510px;
  margin: 0 auto;
  padding: 4rem 0;
}

.vehiculis-titulus {
  height: 5.5rem; /* 88px */
  font-size: 2rem;
  background-color: rgba(0, 0, 0, 0.7);
  color: white;
}

.item {
  padding: 1.5rem 0;
  height: 500px;
}

.unus {
  background-color: rgba(220, 220, 220, 0.2) ; 
}

.duo {
  background-color: rgba(220, 220, 220, 0.8);
}

.tribus {
  background-color: rgba(220, 220, 220, 0.8);
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

</style>
