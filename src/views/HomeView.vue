<template>
  <div class="home">
    <h1 class="text-center text-5xl my-5 text-bold text-emerald-500">FILMES</h1>
    <!--<HelloWorld msg="Welcome to Your Vue.js + TypeScript App" />-->
    <!--<ListaFilmes msg="Filmes para alugar" />-->
    <Pesquisa msg="Filmes para alugar" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import HelloWorld from "@/components/HelloWorld.vue"; // @ is an alias to /src
import ListaFilmes from "@/components/ListaFilmes.vue";
import Pesquisa from "@/components/Pesquisa.vue";

export default defineComponent({
  name: "HomeView",
  components: {
    //HelloWorld,
    //ListaFilmes,
    Pesquisa,
  },
});
</script>
