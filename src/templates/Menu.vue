<template>
  <div class="fullscreen2">
    .
    <div class="mainDiv">
      <div class="contentMainDiv">
        <h3>Menu</h3>
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
      <div class="contentMainDiv">
        <h3>Formule du midi</h3>
        Plat + 3€ = 1 café gourmand
      </div>
    </div>
  </div>
</template>

<script>

  export default {
    data () {
      return {
        contentEntrees: [],
        contentPlats: [],
        contentDesserts: [],
        menuJson: {}
      }
    },
    created () {
      this.menuJson = JSON.parse(window.localStorage.getItem('menuJson'))
      this.contentEntrees = this.menuJson.menu.entree;
      this.contentPlats = this.menuJson.menu.plat;
      this.contentDesserts = this.menuJson.menu.dessert;
      console.log(this.contentEntrees[0].name)
      console.log(this.contentEntrees[0].price)
    }
  }
</script>

<style>
</style>
