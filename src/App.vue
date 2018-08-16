<template>
  <div id="app">
    <ul>
      <li><a href="#" @click="showhome">{{ homeTitle }}</a></li>
      <li><a href="#" @click="showmenu">{{ menuTitle }}</a></li>
      <li><a href="#" @click="showcontact">{{ contactTitle }}</a></li>
	  <li><a href="#" @click="showreservation">{{ reservationTitle }}</a></li>
	  <li><a href="#" @click="showavis">{{ avisTitle }}</a></li>
	  <li><a href="#" @click="showportfolio">{{ portfolioTitle }}</a></li>
      <li><a href="#" @click="showadmin">{{ adminTitle }}</a></li>
    </ul>
	<transition name="slide-fade">
	  <div v-if="home">
	    <Home></Home>
	  </div>
	</transition>
	<transition name="slide-fade">
	  <div v-if="menu">
	    <Menu></Menu>
	  </div>
	</transition>
	<transition name="slide-fade">
	  <div v-if="contact">
	    <Contact></Contact>
	  </div>
	</transition>
	<transition name="slide-fade">
	  <div v-if="reservation">
	    <Reservation></Reservation>
	  </div>
	</transition>
	<transition name="slide-fade">
	  <div v-if="avis">
	    <Avis></Avis>
	  </div>
	</transition>
	<transition name="slide-fade">
	  <div v-if="portfolio">
	    <Portfolio></Portfolio>
	  </div>
	</transition>
	<transition name="slide-fade">
	  <div v-if="admin">
	    <Admin></Admin>
	  </div>
	</transition>
  </div>
</template>

<script>
import Home from './Home.vue'
import Menu from './Menu.vue'
import Contact from './Contact.vue'
import Reservation from './Reservation.vue'
import Avis from './Avis.vue'
import Portfolio from './Portfolio.vue'
import Admin from './Admin.vue'

  export default {
    components: { Home, Menu, Contact, Reservation, Avis, Portfolio, Admin },
    data () {
      return {
        home: true,
		menu: false,
		contact: false,
		reservation: false,
		avis: false,
		portfolio: false,
		admin: false,
		homeTitle: 'Accueil',
		menuTitle: 'La carte',
		contactTitle: 'Contact',
		reservationTitle: 'Reservation',
		avisTitle: 'Avis',
		portfolioTitle: 'Portfolio',
		adminTitle: 'Admin'
      }
    },
    methods: {
      showhome: function () {
	    this.home = true
		this.menu = false
		this.contact = false
		this.reservation = false
		this.avis = false
		this.portfolio = false
		this.admin = false
	  },
	  showmenu: function () {
	    this.home = false
		this.menu = true
		this.contact = false
		this.reservation = false
		this.avis = false
		this.portfolio = false
		this.admin = false
	  },
	  showcontact: function () {
	    this.home = false
		this.menu = false
		this.contact = true
		this.reservation = false
		this.avis = false
		this.portfolio = false
		this.admin = false
	  },
	  showadmin: function () {
	    this.home = false
		this.menu = false
		this.contact = false
		this.reservation = false
		this.avis = false
		this.portfolio = false
		this.admin = true
	  },
	  showreservation: function () {
	    this.home = false
		this.menu = false
		this.contact = false
		this.reservation = true
		this.avis = false
		this.portfolio = false
		this.admin = false
	  },
	  showavis: function () {
	    this.home = false
		this.menu = false
		this.contact = false
		this.reservation = false
		this.avis = true
		this.portfolio = false
		this.admin = false
	  },
	  showportfolio: function () {
	    this.home = false
		this.menu = false
		this.contact = false
		this.reservation = false
		this.avis = false
		this.portfolio = true
		this.admin = false
	  }
    }
  }
</script>

<style>
#app{
  min-height: 100%;
}

html body {
  height: 100%;
  margin: 0;
}

ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
  overflow: hidden;
  background-color: #333;
}

li {
  float: left;
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
  transition: all .3s ease;
}
.slide-fade-leave-active {
  transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateX(10px);
  opacity: 0;
}
</style>