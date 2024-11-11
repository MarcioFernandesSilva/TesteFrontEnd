<template>
  <v-app>
    <v-main>
      <!-- Componente para o Header -->
      <!-- Utilizando Emit para obter o heroi do menu selecionado a partir do metodo getNameHero -->
      <Header @info="getNameHero"></Header>
      <!-- Componente para o Body -->
      <!-- Utilizando prop para passar o objeto que contem as informações do heroi obtido através do Emit acima -->
      <!-- E o objeto selectedHero está padronizado com as informações do Hulk justamente por ser o primeiro heroi selecionado ao abrir a pagina -->
      <Body :selectedHero="selectedHero"></Body>
    </v-main>
  </v-app>
</template>
<script>
import Hulk from "./assets/HULK.png";
  export default{
    data(){
      return{
        // Objeto pré-definido por conta do heroi Hulk ser o primeiro a ser visto ao abrir o site
        selectedHero:{
          name:"Hulk",
          path:Hulk,
          text_body:"Bioscience genius Dr. Bruce Banner focused his major studies on the effects of gamma radiation on humans, working alongside Dr. Betty Ross at a Virginia University lab. Dr. Ross’ father, General “Thunderbolt” Ross of the U.S. Army, channeled Banner’s work into a program to develop weapons for the military, unbeknownst to both doctors. When Banner decided to test what he learned on himself, he triggered a fantastic transformation in himself that resulted in an immense, hulking figure fueled by his own rage. Having destroyed his lab as the creature, and inadvertently harming Ross in the process, Banner slipped away to avoid capture and study by the Army and began a desperate quest for a cure to his bizarre affliction."
        }
      }
    },
    methods:{
      // Metodo que resgata o objeto contendo as informações do heroi selecionado no componente Header.vue no qual é transmitido pelo emit info, e substitui as informações
      // do heroi pré-definido Hulk no objeto selectedHero
      getNameHero(hero){
        this.selectedHero=hero;
      }
    }
  }
</script>
<!-- Estilização de reset do documento e configurações gerais como cor do fundo e a font do documento -->
<style scoped>
*{
  padding: 0;
  margin: 0;
  box-shadow: 0;
  background-color: #101010;
  font-family: Roboto;
  color:#fff
}
</style>
