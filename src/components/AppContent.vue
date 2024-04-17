<template>
  <main class="main-content">
    <section>
      <div class="container">
        <h2>Movies:</h2>
      </div>
      <div class="container">
        <ul>
          <AppCard v-for="movie in store.movies" :key="movie.id" :item="movie" />
        </ul>
      </div>
    </section>
  </main>
</template>

<script>
import {store} from '../store.js'
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
.main-content {
    margin: 20px 15px;
}
</style>