<!-- eslint-disable prettier/prettier -->
<script lang="ts">
import { defineComponent } from "vue";

let filme = {
    Title: "",
    Year: "",
    Rated: "",
    Released: "",
    Runtime: "",
    Genre: "",
    Director: "",
    Writer: "",
    Actors: "",
    Plot: "",
    Language: "",
    Country: "",
    Awards: "",
    Poster: "",
    Ratings: [
        {
            Source: "",
            Value: ""
        },
        {
            Source: "",
            Value: ""
        },
        {
            Source: "",
            Value: ""
        }
    ],
    Metascore: "",
    imdbRating: "",
    imdbVotes: "",
    imdbID: "",
    Type: "",
    DVD: "",
    BoxOffice: "",
    Production: "",
    Website: "",
    Response: "",
};
var title = 'Red';
var apiKey = 'd57d74cb'
fetch('http://www.omdbapi.com/?t=' + title + '&apikey=' + apiKey)
    .then(response => response.json())
    .then(data => filme = data)



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
      <div class="card m-3">
          <h5 class="card-header text-center">Vue 3 fetch data from API</h5>
          <div class="card-body">
          </div>
      </div>
    </div>
  </template>