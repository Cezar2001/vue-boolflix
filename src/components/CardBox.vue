<template>
        <div class="film-post">
            <img 
            class="post-img"
            :src="'https://image.tmdb.org/t/p/original/' + item.poster_path"
            >

            <div class="hover-card">
                <div>
                    <span v-if="item.title">Title: {{item.title}}</span>
                    <span v-else>Title: {{item.name}}</span>
                </div>

                <div>
                    <span v-if="item.original_title">Original Title: {{item.original_title}}</span>
                    <span v-else>Original Title: {{item.original_name}}</span>
                </div>

                <div class="box-flag">Lingua originale: 
                    <span v-if="item.original_language === null">Not Defined</span>
                    <span v-else>
                        {{item.original_language}}
                        <img class="flag" :src="`/flags/${item.original_language}.png`">
                    </span>
                </div> 

                <div>
                    Vote: 
                    <i
                    v-for="index in Math.round(item.vote_average / 2)"
                    :key="index"
                    class="fas fa-star"></i>
                </div>
                <div>Overview: {{item.overview}}</div>
            </div>
        </div>
</template>

<script>
export default {
    props: {
        item: Object,
    },
}
</script>

<style lang="scss" scoped>     
@import '../style/variables.scss';
.film-post{
    height: 350px;
    margin: 5px 2px;
    width: 250px;
    cursor: pointer;

    .post-img{
        width: 100%;
        height: 100%;
    }  

    &:hover{
        background-color: $dark-color;
        overflow: auto;
        color: $white-color;

        .post-img{
            display: none;
        }

        .hover-card{
            display: block;
        
            div{
                padding: 2px;
            }
        }
    }

    .box-flag, span{
        display: flex;
        align-items: center;

        .flag{
            width: 15px;
            height: 15px;
            margin-left: 5px;
        }
    }
}

.hover-card{
    display: none;
    color: $white-color;
    padding: 15px;
}
</style>