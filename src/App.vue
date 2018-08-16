<template>
  <div id="app">
    <ul>
      <li><a href="#" @click="showhome">Home</a></li>
      <li><a href="#" @click="showmenu">Menu</a></li>
      <li><a href="#" @click="showcontact">Contact</a></li>
      <li><a href="#" @click="showadmin">Admin</a></li>
    </ul>
	<transition name="slide-fade">
	  <div v-if="home">
	    HOME
	  </div>
	</transition>
	<transition name="slide-fade">
	  <div v-if="menu">
	    MENU
	  </div>
	</transition>
	<transition name="slide-fade">
	  <div v-if="contact">
	    CONTACT
	  </div>
	</transition>
	<transition name="slide-fade">
	  <div v-if="admin">
	    ADMIN
	  </div>
	</transition>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        home: true,
		menu: false,
		contact: false,
		admin: false
      }
    },
    methods: {
      showhome: function () {
	    this.home = true
		this.menu = false
		this.contact = false
		this.admin = false
	  },
	  showmenu: function () {
	    this.home = false
		this.menu = true
		this.contact = false
		this.admin = false
	  },
	  showcontact: function () {
	    this.home = false
		this.menu = false
		this.contact = true
		this.admin = false
	  },
	  showadmin: function () {
	    this.home = false
		this.menu = false
		this.contact = false
		this.admin = true
	  }
    }
  }
</script>

<style>
#app{

}

ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
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

/* Change the link color to #111 (black) on hover */
li a:hover {
    background-color: #111;
}

/* Les animations d'entrée (« enter ») et de sortie (« leave »)  */
/* peuvent utiliser différentes fonctions de durée et de temps.  */
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