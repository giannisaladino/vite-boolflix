<template>
    <main class="container-lg mt-3 d-flex">
        <section class="container-lg">
            <div>
                <h2>Movies:</h2>
            </div>
            <div>
                <AppCard v-for="movie in store.movies" :key="movie.id" :item="movie" />
            </div>
        </section>

        <section class="container-lg">
            <div>
                <h2>Serie-TV:</h2>
            </div>
            <div>
                <ul class="items-list">
                    <AppCard v-for="tv in store.tvs" :key="tv.id" :item="tv" />
                </ul>
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


</style>