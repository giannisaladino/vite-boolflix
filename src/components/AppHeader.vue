<template>
    <header class="page-header">
        <div class="container">
            <div>
                LOGO
            </div>
            <div>
                <input v-model="query" class="input_search" type="text" placeholder="Cerca...">
                <button @click="getValuesElement" class="btn">Invia</button>
            </div>
        </div>
    </header>
</template>

<script>
import axios from 'axios';
import { store } from '../store';

export default {
    data() {
        return {
            query: ''
        }
    },
    methods: {
        getValuesElement() {
            // console.log(this.store.query);
            axios.get('https://api.themoviedb.org/3/search/movie', {
                params: {
                    api_key: 'edd4a3fe67429d35de6cfe46b5a82652',
                    query: this.query
                }
            }).then((res) => {
                const results = res.data.results;
                // console.log(results);
                store.movies = results;
            })
        }
    },
}
</script>

<style lang="scss" scoped>

.container {
    color: white;
    background-color: black;
    padding: 15px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.input_search {
    padding: 5px;
    margin-right: 10px;
    border-radius: 5px;
    border: none;
}

.btn {
    padding: 5px 8px;
    border-radius: 5px;
    border: none;
}
</style>