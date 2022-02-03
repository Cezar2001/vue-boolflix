<template>
    <div>
        <h1>BOOLFLIX</h1>
        <div>
            <input type="text"
            placeholder="Search"
            v-model="keywordSearch">
            <button @click="$emit('search', keywordSearch)">Search</button>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            keywordSearch: '',
        }
    }
}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';
div {
    padding-top: 15px;
    background-color: black;
    height: 100px;

    h1{
        color: red;
    }
}
</style>