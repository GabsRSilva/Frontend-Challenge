<!-- eslint-disable prettier/prettier -->

<script>
import { ref } from "vue";

export default {
    data() {
      return {
        searchText: '',
        error: '',
        searchReturn: '', 
          title: "",
          year: "",
          iimdbID: "",
          type: "",
          poster: "",
          director: "",
      }
    },
    methods: {
        async search() {
          this.error = '';
          if (this.searchText) {
            var apiKey = 'd57d74cb'
            this.searchReturn = await fetch('http://www.omdbapi.com/?t=' + this.searchText + '&apikey=' + apiKey)
            .then(response => response.json())
            .then(data => {return data})
            console.log(this.searchReturn);

            this.poster = ref(this.searchReturn.Poster);
            this.title = this.searchReturn.Title;
            this.year = this.searchReturn.Year;
            this.iimdbID = this.searchReturn.imdbID;
            this.type = this.searchReturn.Type;
            this.director = this.searchReturn.Director;
            console.log(this.poster,this.title,this.year);
            //var titulo = this.searchReturn.title;
            //console.log(this.titulo);
            // eslint-disable-next-line no-undef
            
          }else{
            this.error = 'O campo está vazio'
          }
        },
    },
    props:{
        msg: String,
    },
  }
</script>
<!-- eslint-disable prettier/prettier -->
<template>
  <h1 class="font-bold text-2xl text-center my-3">{{ msg }}</h1>
  <div class="text-center">
    <input v-model="searchText" type="text" class="rounded-md">
    <button @click="search" class="mx-3 bg-emerald-500 p-2 rounded-md">Pesquisar</button>
  </div>
  <div v-if="this.poster" class="flex items-center my-5 mx-80">
    <img :src="this.poster" alt="Dynamic image poster" class="w-4/12"/>
    <div class="mx-10 font-medium text-xl">
      <h3 class="text-2xl text-emerald-500 mb-3"><strong>{{ this.title }}</strong></h3>
      <p><b>Year: </b>{{ this.year }}</p>
      <p><b>imdbID: </b>{{ this.iimdbID }}</p>
      <p><b>Type: </b>{{ this.type }}</p>
      <p><b>Director: </b>{{ this.director }}</p>
    </div>
  </div>  
</template>
<!-- eslint-disable prettier/prettier -->
<style lang="less">
.d-none{
    display: none;
}
</style>
