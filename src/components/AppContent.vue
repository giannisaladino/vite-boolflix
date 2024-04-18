<template>
    <main class="page-content">
        <section class="container">
            <div class="section-title">
                <h2>FILMS</h2>
            </div>
            <div class="row g-4 d-flex flex-wrap">
                <AppCard v-for="movie in store.movies" :key="movie.id" :item="movie" />
            </div>
        </section>

        <section class="container mt-5 pb-5">
            <div class="section-title">
                <h2>SERIES</h2>
            </div>
            <div class="row g-4 d-flex flex-wrap">
                <AppCard v-for="tv in store.tvs" :key="tv.id" :item="tv" />
            </div>
        </section>
    </main>
</template>

<script>
import { store } from '../store.js'
import AppCard from './AppCard.vue'
export default {
    components: {
        AppCard
    },
    data() {
        return {
            store
        }
    }
}
</script>

<style lang="scss" scoped>
@use 'bootstrap';

.container {
    max-width: 1200px;
}

.page-content {
    background-color: #0F0F0F;
}

.row {
    
}

.section-title {
    padding: 30px 0 ;
    display: flex;
    justify-content: flex-start;
    align-items: center;

    h2 {
        color: white;
        text-decoration: underline;
        font-size: 45px;
        font-family:Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
    }
}

</style>