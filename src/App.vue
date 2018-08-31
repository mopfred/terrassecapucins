<template>
  <div id="app">
    <ul>
      <li><a href="#" @click="showhome">{{ homeTitle }}</a></li>
      <li><a href="#" @click="showmenu">{{ menuTitle }}</a></li>
      <li><a href="#" @click="showcontact">{{ contactTitle }}</a></li>
	  <li><a href="#" @click="showreservation">{{ reservationTitle }}</a></li>
	  <li><a href="#" @click="showavis">{{ avisTitle }}</a></li>
	  <li><a href="#" @click="showportfolio">{{ portfolioTitle }}</a></li>
      <li style="float:right;"><a href="#" @click="showadmin">{{ adminTitle }}</a></li>
    </ul>
	<transition name="slide-fade">
	  <div class="fullscreen" v-if="toshow === 'home'">
	    <BandeauHome></BandeauHome>
	    <Home></Home>
	  </div>
	</transition>
	<transition name="slide-fade">
	  <div class="fullscreen" v-if="toshow === 'menu'">
		<BandeauHome></BandeauHome>
	    <Menu></Menu>
	  </div>
	</transition>
	<transition name="slide-fade">
	  <div class="fullscreen" v-if="toshow === 'contact'">
	    <Contact></Contact>
	  </div>
	</transition>
	<transition name="slide-fade">
	  <div class="fullscreen" v-if="toshow === 'reservation'">
	    <Reservation></Reservation>
	  </div>
	</transition>
	<transition name="slide-fade">
	  <div class="fullscreen" v-if="toshow === 'avis'">
	    <Avis></Avis>
	  </div>
	</transition>
	<transition name="slide-fade">
  	  <div class="fullscreen" v-if="toshow === 'portfolio'">
	    <Portfolio></Portfolio>
	  </div>
	</transition>
	<transition name="slide-fade">
	  <div class="fullscreen" v-if="toshow === 'admin'">
	    <Admin></Admin>
	  </div>
	</transition>
  </div>
</template>

<script>
import BandeauHome from './templates/BandeauHome.vue'
import Home from './templates/Home.vue'
import Menu from './templates/Menu.vue'
import Contact from './templates/Contact.vue'
import Reservation from './templates/Reservation.vue'
import Avis from './templates/Avis.vue'
import Portfolio from './templates/Portfolio.vue'
import Admin from './templates/Admin.vue'

  export default {
    components: { BandeauHome, Home, Menu, Contact, Reservation, Avis, Portfolio, Admin },
    data () {
      return {
	    toshow: 'home',
		homeTitle: 'Accueil',
		menuTitle: 'La carte',
		contactTitle: 'Contact',
		reservationTitle: 'Réservation',
		avisTitle: 'Avis',
		portfolioTitle: 'Portfolio',
		adminTitle: 'Admin'
      }
    },
    methods: {
      showhome: function () {
	    this.toshow = 'home'
	  },
	  showmenu: function () {
	    this.toshow = 'menu'
	  },
	  showcontact: function () {
	    this.toshow = 'contact'
	  },
	  showadmin: function () {
	    this.toshow = 'admin'
	  },
	  showreservation: function () {
	    this.toshow = 'reservation'
	  },
	  showavis: function () {
	    this.toshow = 'avis'
	  },
	  showportfolio: function () {
	    this.toshow = 'portfolio'
	  }
    }
  }
</script>

<style>
html body {
  height: 100%;
  margin: 0;
}

#app {
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0px;
  left: 0px;
  margin: 0;
  padding: 0;
}

.fullscreen {
  /*background-image: url("https://pbs.twimg.com/media/DfkhrO1XUAEYkdw.jpg");*/
  height: 100%;
  
  background-color: grey;
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