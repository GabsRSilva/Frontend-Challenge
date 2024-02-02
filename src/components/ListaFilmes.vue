<!-- eslint-disable prettier/prettier -->
<script lang="ts">
import { defineComponent } from "vue";

let pesquisa = {
    Search:[
      {
      Title: "",
      Year: "",
      imdbID: "",
      Type: "",
      Poster: "",
      }
    ],
};

var title = 'two';
var apiKey = 'd57d74cb'
fetch('http://www.omdbapi.com/?s=' + title + '&apikey=' + apiKey)
    .then(response => response.json())
    .then(data => console.log("Temperatura em Londres: ", data))
    //.then(data => filmes = data)
    

export default defineComponent({
  name: "ListaFilmes",
  props: {
    msg: String,
  },
});
</script>
<!-- eslint-disable prettier/prettier -->

<template>
    <div class="filmes">
      <h1 class="font-bold text-2xl ml-4">{{ msg }}</h1>
    </div>
  </template>