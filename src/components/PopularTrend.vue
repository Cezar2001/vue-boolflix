<template>
    <div>
        <!-- <div
        v-for="popular in popularFilms"
        :key="popular.id"> -->
        <!-- </div> -->
        
        <card-box
            v-for="popular in popularList"
            :key="popular.id"
            :result="popular" />
    </div>
</template>

<script>
import CardBox from './CardBox.vue';
export default {
    components:{
        CardBox
    },
    props: {
        popularList: Array
    }
}
</script>

<style lang="scss" scoped>
div{
    display: flex;
    flex-wrap: wrap;
    padding: 10px 35px;
    margin-bottom: 25px;
}
</style>