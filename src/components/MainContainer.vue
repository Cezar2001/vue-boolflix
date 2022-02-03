<template>
    <div class="film-card">
        <card-box
        v-for="film in filmList"
        :key="film.id"
        :film="film" />
    </div>
</template>

<script>
import CardBox from './CardBox.vue';
export default {
    components: {
        CardBox
    },
    props: {
        filmList: Array
    },
}
</script>

<style lang="scss" scoped>
.film-card{
    display: flex;
    flex-wrap: wrap;
    background-color: #777;
}
</style>