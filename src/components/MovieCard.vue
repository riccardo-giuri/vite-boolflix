<script>
import { movieStore, supportedFlagsCodes } from '../MovieStore';
import LangFlag from "vue-lang-code-flags";
import StarRating from "vue-star-rating";

export default {
    data() {
        return {
            movieStore,
            supportedFlagsCodes
        }
    },

    components: {
        LangFlag,
        StarRating
    },

    props: {
        singleMovie: Object
    }
}
</script>

<template>
    <div class="card_movie">
        <img class="card_img" :src="`https://image.tmdb.org/t/p/w342${singleMovie.poster_path}`" alt="">

        <div class="card_container">
            <ul>
                <li><div> Titolo: {{ singleMovie.title }}</div></li>
                <li><div> Titolo Originale: {{ singleMovie.original_title }}</div></li>
                <li >
                    <div v-if="singleMovie.original_language in supportedFlagsCodes">
                        <span>Lingua: </span>
                        <LangFlag class="bandiera" :iso="`${singleMovie.original_language}`" :squared="false"></LangFlag>
                    </div>
                    <div v-else>
                        Lingua: {{ singleMovie.original_language }}
                    </div>
                </li>
                <li>
                    <star-rating :rating="Math.round((singleMovie.vote_average / 2))" :show-rating="false" :star-size="25" :read-only="true"></star-rating>
                </li>

                <li><div> Sinossi: {{ singleMovie.overview }}</div></li>
            </ul>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    .card_movie {
        width: 342px;
        height: 450px;
        border: 1px solid gray;
        overflow: hidden;
        margin: 0;
        position: relative;
    }

    .card_container:hover {
        opacity: 1;
    }

    .card_img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .card_container {
        width: 100%;
        height: 100%;
        top: 0;
        right: 0;
        position: absolute;
        opacity: 1;
        background-color: rgba(15, 15, 16, 0.751);
        backdrop-filter: blur(5px);
        transition: 0.4s;
        color: white;
        font-size: .85rem;
        padding: 2rem 1.5rem;
        overflow: auto;
    }

    li {
        list-style: none;
        margin-bottom: .3rem;
    }

    ul {
        padding: 0;
    }
</style>