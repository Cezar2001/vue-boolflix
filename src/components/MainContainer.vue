<template>
    <div>
        <h2>ORIGINAL NETFLIX</h2>
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
@import '../style/variables.scss';
h2{
    color: $grey-color;
    margin-bottom: 10px;
}
.film-card{
    display: flex;
    flex-wrap: wrap;
}
</style>