<template>
<div id="mainapp">
  <ul>
    <li><a href="#" @click="showhome">{{ homeTitle }}</a></li>
    <li><a href="#" @click="showmenu">{{ menuTitle }}</a></li>
    <li><a href="#" @click="showportfolio">{{ portfolioTitle }}</a></li>
    <li style="float:right;"><a href="#" @click="showadmin">{{ adminTitle }}</a></li>
  </ul>
  <Bandeau v-bind="bandeauDTO"></Bandeau>
  <transition name="slide-fade">
	<div class="fullscreen" v-if="bandeauDTO.tab === 'home'">
	  <Home></Home>
	</div>
  </transition>
  <transition name="slide-fade">
	<div class="fullscreen" v-if="bandeauDTO.tab === 'menu'">
	  <Menu></Menu>
	</div>
  </transition>
  <transition name="slide-fade">
  	<div class="fullscreen" v-if="bandeauDTO.tab === 'portfolio'">
      <Portfolio></Portfolio>
    </div>
  </transition>
  <transition name="slide-fade">
    <div class="fullscreen" v-if="bandeauDTO.tab === 'admin'">
      <Admin></Admin>
    </div>
  </transition>
</div>
</template>

<script>
import Bandeau from './Bandeau.vue'
import Home from './Home.vue'
import Menu from './Menu.vue'
import Portfolio from './Portfolio.vue'
import Admin from './Admin.vue'

  export default {
    components: { Bandeau, Home, Menu, Portfolio, Admin },
    data () {
      return {
        homeTitle: 'Accueil',
        menuTitle: 'La carte',
        portfolioTitle: 'Portfolio',
        adminTitle: 'Admin',
        bandeauDTO: {
          tab: 'home',
          titleUp: 'Accueil',
          titleDown: 'Bienvenue'
        }
      }
    },
    methods: {
      showhome: function () {
        this.bandeauDTO.tab = 'home'
        this.bandeauDTO.titleUp = 'Accueil'
        this.bandeauDTO.titleDown = 'Bienvenue'
      },
      showmenu: function () {
        this.bandeauDTO.tab = 'menu'
        this.bandeauDTO.titleUp = 'La carte'
        this.bandeauDTO.titleDown = 'La terrasse des capucins'
      },
      showportfolio: function () {
        this.bandeauDTO.tab = 'portfolio'
        this.bandeauDTO.titleUp = 'Portfolio'
        this.bandeauDTO.titleDown = 'Pour vous donner l\'envie de venir'
      },
      showadmin: function () {
        this.bandeauDTO.tab = 'admin'
        this.bandeauDTO.titleUp = 'Administration'
        this.bandeauDTO.titleDown = 'Partie réservée'
      }
    }
  }
</script>

<style>

#mainapp {
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0px;
  left: 0px;
  margin: 0;
  padding: 0;
}

.fullscreen {
  background-color: white;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
  overflow: hidden;
  background-color: #333;
  position: fixed;
  width: 100%;
  z-index: 1000;
}

li {
  float: left;
  height: 5%;
}

li a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

li a:hover {
  background-color: #111;
}

.slide-fade-enter-active {
  transition: all 1s ease;
}

.slide-fade-leave-active {
  transition: all .5s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}

.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateX(10px);
  opacity: 0;
}
</style>
