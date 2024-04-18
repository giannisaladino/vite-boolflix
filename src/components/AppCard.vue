<template>
    <div v-if="item.poster_path !== null" class="item col-lg-3 col-md-4 col-sm-6">
        <!-- item.original_title !== undefined ? item.original_title : item.original_name -->
        <!-- <p>Titolo originale: {{ item.original_title ?? item.original_name }}</p> -->
        <img class="thumb" :src="`https://image.tmdb.org/t/p/w342${item.poster_path}`" alt="">
        <div class="hover d-flex flex-column">
            <span class="title"> <strong>Titolo:</strong> {{ getTitle() }}</span>
            <span><strong>Titolo Originale:</strong> {{ getTitle() }}</span>
            <span class="overview"><strong>Overview:</strong> {{ item.overview }}</span>
            <ul>
                <span><strong>Voto:</strong></span> 
                <li v-for="item in getStars(item.vote_average)">*</li>
                <li v-for="item in getEmptyStars(parseInt(item.vote_average))">-</li>
            </ul>
        </div>
        <!-- <p>{{ item.original_language }}</p> -->
        <!-- <img class="flags" :src="convertFlag(item.original_language)" alt=""> -->
        <!-- <p>Voto medio: {{ item.vote_average }}</p> -->
    </div>
</template>

<script>
export default {
    props: {
        item: {
            type: Object,
            required: true
        }
    },
    methods: {
        getTitle() {
            if (this.item.original_title !== undefined) {
                return this.item.original_title;
            } else {
                return this.item.original_name;
            }
        },
        convertFlag(flagCode) {
            if (flagCode === 'it') {
                return '../flags/ita.svg.png'
            } else if (flagCode === 'en') {
                return '../flags/en.jpeg'
            } else if (flagCode === 'es') {
                return '../flags/es.png'
            } else if (flagCode === 'fr') {
                return '../flags/fr.avif'
            }
        },
        getStars(numero) {
            return Math.floor(numero / 2);
        },
        getEmptyStars(numero) {
            return Math.round(5 - numero / 2);
        }

    }
}
</script>

<style lang="scss" scoped>
.item {
    position: relative;

    .hover {
        opacity: 0;
        background-color: black;
        color: white;
        position: absolute;
        width: 95%;
        height: 100%;
        top: 0;
        gap: 7px;

        .title {
            margin-top: 30px;
        }

        .overview {
            font-size: 10px;
        }
    }
}

.hover:hover {
    opacity: 0.9;
    transition: 200ms;
}

.thumb {
    width: 100%;
    border: 2px solid #FF0000;
}

.thumb:hover {
    border: 5px solid white;
    transition: 300ms;
 }

.flags {
    display: block;
    max-width: 25px;
}

.card {
    margin-bottom: 15px;
}

ul {
    list-style: none;
    display: flex;
    padding: 0;
}
</style>
