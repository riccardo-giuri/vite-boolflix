<script>
import { movieStore, supportedFlagsCodes } from '../MovieStore';
import LangFlag from "vue-lang-code-flags";
import StarRating from "vue-star-rating";

export default {
    components: {
        LangFlag,
        StarRating
    },

    data() {
        return {
            movieStore,
            supportedFlagsCodes         
        }
    }
}
</script>

<template>
    <div class="text-center">
        <h1>MOVIES</h1>
    </div>

    <div class="row row-cols-3 mt-4">
        <div class="col mb-4 h-100" v-for="movie in movieStore.moviesDataList">
            <ul>
                <li><div> {{ movie.title }}</div></li>
                <li><div> {{ movie.original_title }}</div></li>
                <li >
                    <div v-if="movie.original_language in supportedFlagsCodes">
                        <LangFlag class="bandiera" :iso="`${movie.original_language}`" :squared="false"></LangFlag>
                    </div>
                    <div v-else>
                        {{ movie.original_language }}
                    </div>
                </li>
                <li><div> {{ movie.vote_average }}</div></li>
                <li>
                    <star-rating :rating="Math.round((movie.vote_average / 2))" :show-rating="false" :star-size="25"></star-rating>
                </li>
                <li><img :src="`https://image.tmdb.org/t/p/w342${movie.poster_path}`" alt=""></li>
            </ul>
        </div>
    </div>

    <div class="text-center">
        <h1>TV SERIES</h1>
    </div>

    <div class="row row-cols-3 mt-4">

        <div class="col mb-4" v-for="tvSeries in movieStore.tvSeriesDataList">
            <ul>
                <li><div> {{ tvSeries.name }}</div></li>
                <li><div> {{ tvSeries.original_name }}</div></li>
                <li >
                    <div v-if="tvSeries.original_language in supportedFlagsCodes">
                        <LangFlag class="bandiera" :iso="`${tvSeries.original_language}`" :squared="false"></LangFlag>
                    </div>
                    <div v-else>
                        {{ tvSeries.original_language }}
                    </div>
                </li>
                <li><div> {{ tvSeries.vote_average }}</div></li>
                <li><img :src="`https://image.tmdb.org/t/p/w342${tvSeries.poster_path}`" alt=""></li>
            </ul>
        </div>

        <div class="col">

        </div>
    </div>


</template>

<style lang="scss" scoped>
    .bandiera {
        width: 30px;
        height: 30px;
    }

    img {
        width: 342px;
        height: 450px;
        border: 1px solid gray;
    }

    .fa-star {
        width: 20px;
        height: 20px;
        display: inline-block;
        color: black;
    }
</style>