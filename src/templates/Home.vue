<template>
<div class="fullscreen2">
	.
	<div class="mainDiv">
		<div class="contentMainDiv">
			<h3>Infos pratiques</h3>
			<span>11 rue des capucins 62000 Arras <br> 03 21 60 12 17</span>
			<br>
			<span><a href="https://www.google.com/maps/dir/?api=1&amp;destination=terrasse+capucins+11+rue+des+capucins++62000+arras+fr" target="_blank" class="btn-link">Itineraire</a></span>
		</div>
		<div class="separator_line"/>
		<div class="contentMainDiv">
			<h3>Horaires</h3>
			<div class="content">
				<span class="spanContent">Lundi-Jeudi</span>
				<span class="sepContent"/>
				<span class="spanContent">11h45 - 14h00</span>
			</div>
			<div class="content">
				<span class="spanContent">Vendredi-Samedi</span>
				<span class="sepContent"/>
				<span class="spanContent">11h45 - 14h00<br>18h45 - 00h00</span>
			</div>
			<div class="content">
				<span class="spanContent">Dimanche</span>
				<span class="sepContent"/>
				<span class="spanContent">Fermé</span>
			</div>
		</div>
		<div class="separator_line"/>
		<div class="contentMainDiv">
			<h3>Cuisine</h3>
			Gastronomique, Française
		</div>
		<div class="separator_line"/>
		<div class="contentMainDiv">
			<h3>Caractéristiques</h3>
			Plats à emporter, Réservations, Terrasse, Places assises, Service en salle, Chaises hautes disponibles, Sert de l'alcool, Bières & Vins, Accepte les cartes bancaires
		</div>
	</div>
</div>
</template>

<script>
  export default {
    data () {
      return {
	    
      }
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
  min-width:400px;
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
