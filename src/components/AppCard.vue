<template>
    <li class="card">
        <div class="card-body">
            <p>{{ item.title }}</p>
            <p>{{ item.name }}</p>
            <p>{{ item.original_title }}</p>
            <p>{{ item.original_name }}</p>
            <p>{{ item.original_language }}</p>
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
    }
}
</script>

<style lang="scss" scoped>
.card {
    margin-bottom: 15px;
}
</style>
