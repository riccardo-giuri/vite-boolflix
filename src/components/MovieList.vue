<script>
import { movieStore, supportedFlagsCodes } from '../MovieStore';

export default {
    data() {
        return {
            movieStore,
            supportedFlagsCodes
        }
    }
}
</script>

<template>
    <div class="row row-cols-3 mt-4">
        <div class="col mb-4" v-for="movie in movieStore.moviesDataList">
            <ul>
                <li><div> {{ movie.title }}</div></li>
                <li><div> {{ movie.original_title }}</div></li>
                <li><div> {{ movie.original_language }}</div></li>
                <li><div> {{ movie.vote_average }}</div></li>
            </ul>
        </div>
    </div>
</template>

<style lang="scss" scoped>

</style>