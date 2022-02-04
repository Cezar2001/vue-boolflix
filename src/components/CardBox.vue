<template>
        <div class="film-post">
            <img 
            :src="'https://image.tmdb.org/t/p/original/' + film.poster_path"
            >

            <div class="hover-card">
                <div>Titolo: {{film.title}}</div>
                <div>Titolo originale: {{film.original_title}}</div>
                <div>Lingua originale: {{film.original_language}}
                    <img class="flag" :src="`/flags/${film.original_language}.png`">
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

    img{
        width: 100%;
        height: 100%;
    }  

    &:hover{
        background-color: black;
        overflow: auto;
        color: white;

        img{
            display: none;
        }

        .hover-card{
            display: block;
        
            div{
                padding: 2px;
            }

            .flag{
                height: 25px;
                height: 20px;
            }
        }
    }
}

.hover-card{
    display: none;
    color: white;
    padding: 15px;
}
</style>