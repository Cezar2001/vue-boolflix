<template>
    <div>
        <h2>ORIGINAL NETFLIX</h2>
        <div class="trend">  
            <card-box
            v-for="film in filmList"
            :key="film.id"
            :item="film" />

            <card-box
            v-for="series in seriesList"
            :key="series.id"
            :item="series" />
            
            <div class="scroll-film">
                <h2>TREND</h2>
                <popular-trend 
                :popularList="popularList"/>
            </div>

            <div class="scroll-series">
                <h2>Popular Now</h2>
                <popular-trend 
                :popularTvList="popularTvList"/>
            </div>
        </div>
    </div>
</template>

<script>
import CardBox from './CardBox.vue';
import PopularTrend from './PopularTrend.vue';

export default {
    components: {
        CardBox,
        PopularTrend,
    },
    props: {
        filmList: Array,
        seriesList: Array,
        popularList:Array,
        popularTvList: Array,
    },
}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';
h2{
    color: $grey-color;
}

h2:first-child{
    margin-bottom: 10px;
}

.trend{
    display: flex;
    flex-wrap: wrap;

    h2{
     margin: 10px 0;
    }
    
    .scroll-film, 
    .scroll-series{
        display: flex;
        flex-wrap: wrap;
        overflow-x: auto;
    }
}
</style>