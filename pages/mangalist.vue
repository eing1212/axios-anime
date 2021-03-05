<template>
  <div>
    <h1>manga page</h1>
    <input type="button" value="Load Data" @click="loadmanga" />

     
    {{mangaList}} 
    
    <!-- <h1 v-for="manga in mangaList" :key="manga.id"></h1>
    `${{manga.title}}` -->
    
      <!-- <ul v-for="manga in mangaList" :key="manga.mal_id">
        <li>
        {{ manga.title }} -->
   
<!-- <a
        :href="
          'https://www.google.com/maps?q=' +
            manga.address.geo.lat +
            ',' +
            manga.address.geo.lng
        "
        target="_blank"
      >
          ที่อยู่
        </a> -->
        <!-- :href="https://www.google.co.th/maps/@"+
manga.address.geo.lat
manga.address.geo.lng
"  -->
        <!-- </li>
      </ul>
   -->
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      mangaList: "1",
    };
  },
  methods: {
    loadmanga() {
      let url = "https://api.jikan.moe/v3/top/manga";
      axios
        .get(url)
        .then((response) => {
          this.mangaList = response.data;
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>

<style>
</style>
