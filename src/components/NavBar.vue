<template>
    <div class="container">
        <div>
            <h1>BOOLFLIX</h1>
            <ul>
                <li>Home</li>
                <li>Serie TV</li>
                <li>Film</li>
                <li>Original</li>
                <li>Aggiunti di recente</li>
                <li>La mia lista</li>
            </ul>
        </div>
        <div>
            <input type="text"
            placeholder="Search"
            v-model="keywordSearch">

            <div  
            @click="$emit('search', keywordSearch)"
            class="search">
                <i class="fas fa-search"></i>
            </div>

            <span>Bambini</span>

            <div class="circle">1</div>

            <i class="fas fa-bell"></i>

            <img class="neflix-pic" :src="`/flags/netflixpic.png`">

            <i class="fas fa-caret-down"></i>
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
.container {
    height: 80px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    color: $grey-color;

    div{
        display: flex;
        align-items: center;

        h1{
            color: $red-color;
        }

        ul{
            display: flex;
            margin-left: 25px;
        }

        li{
            list-style: none;
            margin: 10px;

            &:hover{
                color: $white-color;
            }
        }

        input{
            background: $dark-grey-color;
            border: 1px $grey-color solid;
            color: $white-color;
            border-radius: 10px;
            margin-right: 5px;
            padding: 5px;
        }

        .search{
            padding: 5px 0;   
        }

        .circle{
            position: relative;
            top: -3px;
            left: 27px;
            width: 10px;
            height: 10px;
            border-radius: 50%;
            font-size: 10px;
            padding: 2px 0 3px 2px;
            color: $white-color;
            background-color: $red-color;
        }

        i, span{
            margin: 0 8px;

            &:hover{
                color: $white-color;
            }
        }

        img{
            height: 30px;
            margin: 0 5px;
            
            &:hover{
                border: 1px $white-color solid;
            }
        }
    }
}
</style>