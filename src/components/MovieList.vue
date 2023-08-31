<script>
import { movieStore, supportedFlagsCodes } from '../MovieStore';
import MovieCard from './MovieCard.vue';
import TvSeriesCard from './TvSeriesCard.vue';
import LangFlag from "vue-lang-code-flags";
import StarRating from "vue-star-rating";

export default {
    components: {
        LangFlag,
        StarRating,
        MovieCard,
        TvSeriesCard
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
    <h1>MOVIES</h1>

    <div class="row row-cols-3 mt-4">
        <div class="col mb-4 h-100" v-for="movie in movieStore.moviesDataList">
            <MovieCard :singleMovie="movie"></MovieCard>
        </div>
    </div>

    <h1>TV SERIES</h1>

    <div class="row row-cols-3 mt-4">

        <div class="col mb-4" v-for="tvSeries in movieStore.tvSeriesDataList">
            <TvSeriesCard :singletvSeries="tvSeries"></TvSeriesCard>
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
        overflow: hidden;
    }

    .fa-star {
        width: 20px;
        height: 20px;
        display: inline-block;
        color: black;
    }

    h1 {
        font-size: 45px;
        color: white;
        text-align: center;
    }
</style>