<template>
    <li class="card">
        <div class="card-body">
            <p>{{ item.title }}</p>
            <p>{{ item.name }}</p>
            <p>{{ item.original_title }}</p>
            <p>{{ item.original_name }}</p>
            <!-- <p>{{ item.original_language }}</p> -->
            <img :src="convertFlag(item.original_language)" alt="">
            <p>{{ item.vote_average }}</p>
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

img {
    max-width: 25px;
}

.card {
    margin-bottom: 15px;
}
</style>
