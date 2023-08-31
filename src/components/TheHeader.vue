<script>
import MovieSearch from './MovieSearch.vue';

export default {

    components: {
        MovieSearch
    },

    data() {
        return {
            navData: [
                { link: "Home" },
                { link: "Film" },
                { link: "Serie Tv" },
                { link: "Originali" },
                { link: "Mia Lista" },
            ]
        }
    }
}
</script>

<template>
    <header class="d-flex align-items-center justify-content-between">
        <div class="d-flex align-items-center">
            <h1 class="text-danger me-5">BoolFlix</h1>

            <ul class="navbar-nav">
                <div class="container-fluid d-flex gap-4">
                    <li class="nav-item" v-for="linkData in navData">
                        <a href="#" class="nav-link">{{ linkData.link }}</a>
                    </li>
                </div>
            </ul>
        </div>

        <div>
            <MovieSearch></MovieSearch>
        </div>
    </header>
</template>

<style lang="scss" scoped>
    ul {
        color: white;
    }

    h1 {
        font-size: 50px;
    }
</style>