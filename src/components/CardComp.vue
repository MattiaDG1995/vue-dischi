<template>
    <div class="colon p-2 text-center">
        
        <div class="card  p-2 fw-bold">
        <img :src="card.poster" class="card-img-top" alt="...">
        <div class="card-body">
            <h5 class="card-title text-white">{{card.title}}</h5>
            <p class="card-text text-dark">{{card.author}}</p>
            <p class="card-text text-dark">{{card.year}}</p>
        </div>
        </div>
       

        
    </div>
</template>

<script>
    export default {
        name: 'CardComp',
        props:{
            card: Object
        }
    }
</script>

<style lang="scss" scoped>

    .colon{
        width: calc(100% / 5);
        img{
            aspect-ratio: 1/1;
        }
    }
    .card{
        background-color: rgba(46, 58, 70, 1);
        height: 380px;
   
    }
</style>