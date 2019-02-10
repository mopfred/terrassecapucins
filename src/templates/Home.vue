<template>
<div class="fullscreen2">
	.
	<div class="mainDiv">
		<div class="contentMainDiv">
			<h3>Du frais sans se lasser...</h3>
			Tout commence par le mélange de l’envie d’entreprendre et la passion de bien manger.. ( Comme Chez Mamie)<br/>
      En découle le projet de La Terrasse Des Capucins,  un décor sobre sans trop de chichi, une cuisine simple mais tellement gourmande et enfin une envie débordante de faire plaisir à notre clientèle.<br/>
      Ensuite on s’est posé la question suivante , “Comment avoir que des PRODUITS FRAIS à notre carte?”<br/>
      On a trouvé la réponse : Une Carte à l’ardoise qui change TOUTE LES SEMAINES avec une planche apéritive, 4 plats et 3 desserts.<br/>
      On vous en a déjà dit pas mal... on vous laisse venir découvrir par vous même !!<br/>
      <br/>Au plaisir de vous accueillir,<br/>
      L’équipe de La Terrasse.
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
