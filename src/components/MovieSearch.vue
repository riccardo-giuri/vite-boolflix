<script>
import axios from "axios";
import { movieStore } from "../MovieStore";

export default {
    data() {
        return {
            movieStore,
            searchText: ""
        }
    },

    methods: {
        buildURL() {
            
        },

        fetchMoviesList(textToSearch) {

            if (textToSearch !== "" && textToSearch !== null) {
                axios.get("https://api.themoviedb.org/3/search/movie", 
            {
                params: {
                    api_key: "4ae347e97d0eb3c81af3a0abd3b73614",
                    query: textToSearch,
                    language: "it-IT",
                }
            }).then((response) => {
                this.movieStore.moviesDataList = response.data.results;
            })
            }
        }
    }
};
</script>

<template>
    <div class="input-group">
        <input type="text" placeholder="Cerca film/serie tv" v-model="searchText">
        <button class="btn btn-outline-secondary rounded-0" type="button" @click="fetchMoviesList(searchText)">Cerca</button>
    </div>
</template>

<style lang="scss" scoped>

</style>