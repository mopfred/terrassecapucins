<template>
  <div class="fullscreen2" v-if="authenticated === 'false'">
    .
    <div class="mainDiv">
      <div class="contentMainDiv">
        <h1>Authentification</h1>
        <input type="text" name="username" v-model="input.username" placeholder="Username" />
        <input type="password" name="password" v-model="input.password" placeholder="Password" />
        <button type="button" v-on:click="login()">Login</button>
      </div>
    </div>
  </div>
  <div class="fullscreen2" v-else-if="authenticated === 'true'">
    .
    <div class="mainDiv">
      <div class="contentMainDiv">
        <h3>Authentifié</h3>
          <label for="entreesButton">Entrées</label>
          <button id="entreesButton" type="button" v-on:click="addBlock('entrees')">+</button>
          <div id="entrees">
          </div>
          <br/>
          <label for="platsButton">Plats</label>
          <button id="platsButton" type="button" v-on:click="addBlock('plats')">+</button>
          <div id="plats">
          </div>
          <br/>
          <label for="dessertsButton">Desserts</label>
          <button id="dessertsButton" type="button" v-on:click="addBlock('desserts')">+</button>
          <div id="desserts">
          </div>
          <br/>
          <button type="button" v-on:click="maj()">Mise à jour</button>
      </div>
    </div>
  </div>
</template>

<script>
  
  export default {
    data() {
      return {
        authenticated: 'false',
        input: {
          username: "",
          password: ""
        },
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
    },
    methods: {
      login() {
        if(this.input.username != "" && this.input.password != "") {
          if(this.input.username == "admin" && this.input.password == "admin") {
            this.authenticated="true"
          }
        }
      },
      addBlock(type){
        var addBlockMainDiv = document.createElement('div');
        addBlockMainDiv.id = type + 'addBlockMainDiv';
        addBlockMainDiv.className = 'blockClass';
        
        var labelName = document.createElement('label');
        labelName.htmlFor = type + 'Name';
        labelName.innerHTML='Nom: ';
        addBlockMainDiv.appendChild(labelName);
        
        var textName = document.createElement('input');
        textName.type='text';
        textName.id = type + 'Name';
        textName.name = type + 'Name';
        addBlockMainDiv.appendChild(textName);
        
        var labelPrice = document.createElement('label');
        labelPrice.htmlFor = type + 'Price';
        labelPrice.innerHTML=' Prix: ';
        addBlockMainDiv.appendChild(labelPrice);
        
        var textPrice = document.createElement('input');
        textPrice.type='text';
        textPrice.id = type + 'Price';
        textPrice.name = type + 'Price';
        addBlockMainDiv.appendChild(textPrice);
        
        document.getElementById(type).appendChild(addBlockMainDiv);
        textName.focus();        
      },
      maj() {
        var entreesName = document.getElementsByName("entreesName");
        var platsName = document.getElementsByName("platsName");
        var dessertsName = document.getElementsByName("dessertsName");
        
        var entreesPrice = document.getElementsByName("entreesPrice");
        var platsPrice = document.getElementsByName("platsPrice");
        var dessertsPrice = document.getElementsByName("dessertsPrice");
        
        for(var i = 0; i < this.contentEntrees.length; i++){
          this.contentEntrees.shift()
        }
        
        for(var i = 0; i < entreesName.length; i++){
          var template = {name:"",price:""}
          template.name = entreesName[i].value
          template.price = entreesPrice[i].value
          
          this.contentEntrees[i] = template
        }
        for(var i = 0; i < platsName.length; i++){
          var template = {name:"",price:""}
          template.name = platsName[i].value
          template.price = platsPrice[i].value
          
          this.contentPlats[i] = template
        }
        for(var i = 0; i < dessertsName.length; i++){
          var template = {name:"",price:""}
          template.name = dessertsName[i].value
          template.price = dessertsPrice[i].value
          
          this.contentDesserts[i] = template
        }
        
        const data = JSON.stringify(this.menuJson)
        console.log(data)
        window.localStorage.setItem('menuJson', data);
      }
    }
  }
</script>

<style>

.blockClass{
  padding: 10px;
  min-width: 400px;
}
</style>
