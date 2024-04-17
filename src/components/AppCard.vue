<template>
    <li class="card">
        <div class="card-body">
            <img class="thumb" :src="`https://image.tmdb.org/t/p/w342${item.poster_path}`" alt="">
            <p>Titolo: {{ item.title }}</p>
            <p>{{ item.name }}</p>
            <p>Titolo originale: {{ item.original_title }}</p>
            <p>{{ item.original_name }}</p>
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
        }
    }
}
</script>

<style lang="scss" scoped>
.thumb {
    max-width: 100px;
}

.flags {
    max-width: 25px;
}

.card {
    margin-bottom: 15px;
}
</style>
