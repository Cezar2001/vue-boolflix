<template>
    <div>
        <div
        v-for="popular in popularFilms"
        :key="popular.id"></div>
    </div>
</template>

<script>
export default {
    props: {
        popularFilms: Array
    }
}
</script>

<style lang="scss" scoped>

</style>