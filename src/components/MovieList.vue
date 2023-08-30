<script>
import { movieStore, supportedFlagsCodes } from '../MovieStore';
import LangFlag from "vue-lang-code-flags";

export default {
    components: {
        LangFlag
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
        <div class="col mb-4" v-for="movie in movieStore.moviesDataList">
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
            </ul>
        </div>
    </div>

    <div class="text-center">
        <h1>TV SERIES</h1>
    </div>

    <div class="row row-cols-3 mt-4">

        <div class="col mb-4" v-for="movie in movieStore.tvSeriesDataList">
            <ul>
                <li><div> {{ movie.name }}</div></li>
                <li><div> {{ movie.original_name }}</div></li>
                <li >
                    <div v-if="movie.original_language in supportedFlagsCodes">
                        <LangFlag class="bandiera" :iso="`${movie.original_language}`" :squared="false"></LangFlag>
                    </div>
                    <div v-else>
                        {{ movie.original_language }}
                    </div>
                </li>
                <li><div> {{ movie.vote_average }}</div></li>
            </ul>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    .bandiera {
        width: 30px;
        height: 30px;
    }
</style>