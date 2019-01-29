<template>
  <div class="fullscreen2">
    .
    <div class="mainDiv">
      <div class="contentMainDiv">
        <h3>Entrées</h3>
        <div v-for="(item, key) in this.contentEntrees" class="content">
          <span class="spanContent">{{item.name}}</span>
		  <span class="sepContent"/>
		  <span class="spanContent">{{item.price}} €</span>
        </div>
      </div>
      <div class="separator_line"/>
      <div class="contentMainDiv">
        <h3>Plats</h3>
        <div v-for="(item, key) in this.contentPlats" class="content">
          <span class="spanContent">{{item.name}}</span>
		  <span class="sepContent"/>
		  <span class="spanContent">{{item.price}} €</span>
        </div>
      </div>
      <div class="separator_line"/>
      <div class="contentMainDiv">
        <h3>Desserts</h3>
        <div v-for="(item, key) in this.contentDesserts" class="content">
          <span class="spanContent">{{item.name}}</span>
		  <span class="sepContent"/>
		  <span class="spanContent">{{item.price}} €</span>
        </div>
      </div>
      <div class="separator_line"/>
    </div>
  </div>
</template>

<script>
  import menuJson from '../json/menu.json';

  export default {
    data () {
      return {
        menuJson
      }
    },
    created () {
      this.contentEntrees = menuJson.menu.entree;
      this.contentPlats = menuJson.menu.plat;
      this.contentDesserts = menuJson.menu.dessert;
    }
  }
</script>

<style>
.fullscreen2 {
  height: 100%;
  width: 100%;

  text-align: center;
  color: white;

  background-color: white;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}



.small_separator_line {
  height: 1px;
	border-bottom: 1px solid #b3b3b3;
	margin-left: 40%;
	margin-right: 40%;
	margin-top: 10px;
	margin-bottom: 10px;
}

</style>
