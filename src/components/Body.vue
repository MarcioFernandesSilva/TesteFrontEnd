<template>
    <v-container fluid class="pt-16">
        <v-responsive>
            <v-row class="d-flex justify-center">
                <!-- Todas as colunas utilizando o sistema de grid para ser responsivo para os devidos dispositivos -->
                <v-col cols="12" xs="12" sm="12" md="12" lg="12" xl="12" xxl="12" class="d-flex justify-center">
                    <!-- Titulo contendo o nome do heroi obtido através do objeto selectedHero enviado do App.vue -->
                    <!-- Também feito uma formatação prévia por causa do hifén no nome de herois, como por exemplo Spider-Man -->
                    <h1 id="title" class="text-h2 text-center">{{ formatHeroName(selectedHero.name.replace('-',' ')) }}</h1>
                </v-col>
                <v-col cols="12" xs="12" sm="12" md="12" lg="4" xl="4" xxl="4" class="d-flex justify-center">
                    <!-- Tag de imagem contendo o caminho da imagem do heroi obtido através do objeto selectedHero enviado do App.vue -->
                    <img :src="selectedHero.path" :alt="selectedHero.name" class="h-75">
                </v-col>
                <v-col cols="10" xs="10" sm="10" md="10" lg="4" xl="4" xxl="4" class="d-flex justify-center">
                    <!-- Tag de paragrafo contendo o texto do heroi selecionado, obtido através do objeto selectedHero enviado do App.vue -->
                    <p>{{ selectedHero.text_body }}</p>
                </v-col>
            </v-row>
        </v-responsive>
    </v-container>
</template>
<script>
export default{
    props:{
        // Prop recebida do App.vue contendo o objeto com as informações do heroi selecionado
        selectedHero:Object
    },
    methods:{
        // Metodo para formatar o nome do heroi selecionado para fazer com que cada palavra do seu nome composto esteja com a primeira letra maiuscula
        formatHeroName(name){
            return name.toLowerCase().split(' ').map(function(word) { 
                return word.charAt(0).toUpperCase() + word.slice(1); 
            }).join(' ');
        }
    }
}
</script>
<style>
/* Fonte unica atribuida ao id title */
#title{
    font-family: Oswald !important;
    font-weight: bold;
}
</style>