<template>
  <div class="fullscreen2">
    .
    <div class="mainDiv">
      <div class="contentMainDiv">
        <h3>Entrées</h3>
        {{contentEntrees}}
        <!--tr v-for="(item) in contentEntrees">
          <td>item</td>
        </tr-->
      </div>
      <div class="separator_line"/>
      <div class="contentMainDiv">
        <h3>Plats</h3>
        {{contentPlats}}
      </div>
      <div class="separator_line"/>
      <div class="contentMainDiv">
        <h3>Desserts</h3>
        {{contentDesserts}}
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

.mainDiv{
  border: 4px solid #e6e6e6;
  margin-left: 30%;
  margin-right: 30%;
  margin-bottom: 10px;
  padding-bottom: 10px;
}

.content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  text-align: center;
}

.spanContent {
	width: 100%;
	margin-bottom: 5px;
}

.contentMainDiv{
  text-align: center;
  color:black;
  height: auto;
  overflow: hidden;
}

.sepContent {
    height: 2px;
    width: 100%;
    background-image: radial-gradient(circle closest-side, #BBBBBB 99%, rgba(0, 0, 0, 0) 1%);
    background-size: 6px 3px;
}

.separator_line {
    height: 1px;
	border-bottom: 1px solid #b3b3b3;
	margin-left: 25%;
	margin-right: 25%;
	margin-top: 10px;
	margin-bottom: 10px;
}
</style>
