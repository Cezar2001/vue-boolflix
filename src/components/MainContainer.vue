<template>
    <div class="film-card">
        <card-box
        v-for="film in filmList"
        :key="film.id"
        :item="film" />

        <card-box
        v-for="series in seriesList"
        :key="series.id"
        :item="series" />
    </div>
</template>

<script>
import CardBox from './CardBox.vue';
export default {
    components: {
        CardBox
    },
    props: {
        filmList: Array,
        seriesList: Array,
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