<template>
    <li class="card">
        <div class="card-body">
            <p>Titolo: {{ getTitle() }}</p>
            <!-- item.original_title !== undefined ? item.original_title : item.original_name -->
            <!-- <p>Titolo originale: {{ item.original_title ?? item.original_name }}</p> -->
            <p>Titolo originale: {{ getTitle() }}</p>
            <img class="thumb" :src="`https://image.tmdb.org/t/p/w342${item.poster_path}`" alt="">
            <!-- <p>{{ item.original_language }}</p> -->
            <img class="flags" :src="convertFlag(item.original_language)" alt="">
            <p>Voto medio: {{ item.vote_average }}</p>
        </div>
    </li>
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
            if(this.item.original_title !== undefined) {
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

    }
}
</script>

<style lang="scss" scoped>
.thumb {
    max-width: 100px;
}

.flags {
    display: block;
    max-width: 25px;
}

.card {
    margin-bottom: 15px;
}
</style>
