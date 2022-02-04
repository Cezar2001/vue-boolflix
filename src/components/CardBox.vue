<template>
        <div class="film-post">
            <img 
            class="post-img"
            :src="'https://image.tmdb.org/t/p/original/' + film.poster_path"
            >

            <div class="hover-card">
                <div>
                    <span v-if="film.title">Title: {{film.title}}</span>
                    <span v-else>Title: Not Defined</span>
                </div>

                <div>
                    <span v-if="film.title">Original Title: {{film.original_title}}</span>
                    <span v-else>Original Title: Not Defined</span>
                </div>
                
                <div class="box-flag">Lingua originale: 
                    <span v-if="film.original_language === null">Not Defined</span>
                    <span v-else>
                        {{film.original_language}}
                        <img class="flag" :src="`/flags/${film.original_language}.png`">
                    </span>
                </div>      
                <div>Voto: {{film.vote_average}}</div>
                <div>Overview: {{film.overview}}</div>
            </div>
        </div>
</template>

<script>
export default {
    props: {
        film: Object
    },
}
</script>

<style lang="scss" scoped>     
.film-post{
    height: 350px;
    margin: 25px;
    width: 250px;
    border: 5px white solid;
    cursor: pointer;

    .post-img{
        width: 100%;
        height: 100%;
    }  

    &:hover{
        background-color: black;
        overflow: auto;
        color: white;

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
    color: white;
    padding: 15px;
}
</style>