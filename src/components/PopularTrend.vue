<template>
<div>
    <div class="trend"> 
        <card-box
        v-for="popular in popularList"
        :key="popular.id"
        :item="popular" />

        <card-box
        v-for="tv in popularTvList"
        :key="tv.id"
        :item="tv" />
    </div>
</div>
</template>

<script>
import CardBox from './CardBox.vue';
export default {
    components:{
        CardBox
    },
    props: {
        popularList: Array,
        popularTvList: Array,
    }
}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';
.trend{
    display: flex;
}
</style>