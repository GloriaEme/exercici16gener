<template>
  <v-container fluid>
      <v-row>
          <v-col class="block block1" align="center">
              Hola,
          </v-col>
      </v-row>
      <v-row>
          <v-col class="block block2" align="center">
              Com et dius?
              <v-text-field
              color="white"
              placeholder="p.e. Gloria"
              style="max-width:400px" outlined rounded 
              v-model="nom"
              ></v-text-field>
          </v-col>
      </v-row>
      <v-row>
          <v-col class="block block3" align="center">
              Quina edat tens?
              <v-text-field
              color="white"
              placeholder="p.e. 22"
              style="max-width:400px" outlined rounded
              v-model="edat"
              ></v-text-field>
          </v-col>
      </v-row>
      <v-row>
          <v-col class="block block4" align="center">
              Tens e-mail?
              <v-text-field
              color="white"
              placeholder="p.e. exemple@maoil.com"
              style="max-width:400px" outlined rounded
              v-model="email"
              ></v-text-field>
          </v-col>
      </v-row>
      <v-row>
          <v-col class="block block5" align="center">
              I telèfon?
              <v-text-field
              color="white"
              placeholder="p.e. 666666666"
              style="max-width:400px" outlined rounded
              v-model="telefon"
              ></v-text-field>
          </v-col>
      </v-row>
      <v-row>
          <v-col class="block block6" align="center">
              De què treballes?
              <v-text-field
              color="white"
              placeholder="p.e. electricista"
              style="max-width:400px" outlined rounded
              v-model="feina"
              ></v-text-field>
          </v-col>
      </v-row>
      <v-row>
          <v-col class="block block7" align="center">
              <p v-if="totPle" style="max-width:500px;text-align: left">
                  En/a {{ nom }} és {{ feina }} i té {{ edat }} anys. Podeu contactar amb ell/a a través del telèfon {{ telefon }} o de l'email {{ email }}.
              </p>
              <p v-else>Cal que emplenis el formulari</p>
              <br>
              <p>{{ elTextFinal }}</p>
          </v-col>
      </v-row>
  </v-container>
</template>

<script>
export default{
  data(){
      return{
          nom:"",
          edat:"",
          email:"",
          telefon:"",
          feina:""
      }
  },
  computed:{
      totPle(){
          return this.nom!=""
          &&this.edat!=""
          &&this.telefon!=""
          &&this.feina!=""
          &&this.email!=""
      },
      elTextFinal(){
          return this.nom
          +" és "
          +this.feina
          +" i té "
          +this.edat
          +" . Podeu contactar-hi a través del telèfon "
          +this.telefon
          +" o bé a través de l'email "
          +this.email
          +"."
      }
  },
}
</script>

<style scoped>
.block{
  min-height: 70vh;
  padding-top: 20vh;
  padding-bottom: 20vh;
  font-size:10vh;
  color:white;
}
.block1{
  background-color: rgb(132, 175, 132);
}
.block2{
  background-color: rgb(44, 86, 44);
}
.block3{
  background-color: rgb(77, 129, 157);
}
.block4{
  background-color: rgb(50, 69, 80);
}
.block5{
  background-color: rgb(77, 202, 77);
}
.block6{
  background-color: rgb(53, 32, 116);
}
.block7{
  background-color: rgb(127, 46, 127);
}
</style>
