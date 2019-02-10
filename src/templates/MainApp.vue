<template>
<div id="mainapp">
  <ul>
    <li><a href="#" @click="showHome">{{ homeTitle }}</a></li>
    <li><a href="#" @click="showInfos">{{ infosTitle }}</a></li>
    <li><a href="#" @click="showMenu">{{ menuTitle }}</a></li>
    <li><a href="#" @click="showPortfolio">{{ portfolioTitle }}</a></li>
    <li style="float:right;"><a href="#" @click="showAdmin">{{ adminTitle }}</a></li>
  </ul>
  <Bandeau v-bind="bandeauDTO"></Bandeau>
  <transition name="slide-fade">
	<div class="fullscreen" v-if="bandeauDTO.tab === 'home'">
	  <Home></Home>
	</div>
  </transition>
  <transition name="slide-fade">
	<div class="fullscreen" v-if="bandeauDTO.tab === 'infos'">
	  <Infos></Infos>
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
import Infos from './Infos.vue'

  export default {
    components: { Bandeau, Home, Infos, Menu, Portfolio, Admin },
    data () {
      return {
        homeTitle: 'Accueil',
        infosTitle: 'Informations',
        menuTitle: 'La carte',
        portfolioTitle: 'Portfolio',
        adminTitle: 'Admin',
        bandeauDTO: {
          tab: 'home',
          titleUp: 'La terrasse des capucins',
          titleDown: 'Accueil'
        }
      }
    },
    methods: {
      showHome: function () {
        this.bandeauDTO.tab = 'home'
        this.bandeauDTO.titleUp = 'La terrasse des capucins'
        this.bandeauDTO.titleDown = 'Accueil'
      },
      showInfos: function () {
        this.bandeauDTO.tab = 'infos'
        this.bandeauDTO.titleUp = 'La terrasse des capucins'
        this.bandeauDTO.titleDown = 'Informations pratiques'
      },
      showMenu: function () {
        this.bandeauDTO.tab = 'menu'
        this.bandeauDTO.titleUp = 'La terrasse des capucins'
        this.bandeauDTO.titleDown = 'La carte'
      },
      showPortfolio: function () {
        this.bandeauDTO.tab = 'portfolio'
        this.bandeauDTO.titleUp = 'La terrasse des capucins'
        this.bandeauDTO.titleDown = 'Portfolio'
      },
      showAdmin: function () {
        this.bandeauDTO.tab = 'admin'
        this.bandeauDTO.titleUp = 'La terrasse des capucins'
        this.bandeauDTO.titleDown = 'Administration'
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

.slide-fade-enter, .slide-fade-leave-to {
  transform: translateX(10px);
  opacity: 0;
}
</style>
