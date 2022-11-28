<template>
    <div>
        <div class="container mt-4">
            <select name="" id="" v-model="genere" @change="filtro">
                <option value="All">All</option>
                <option :value="elem" v-for="(elem, index) in arrayGeneri" :key="index">{{elem}}</option>

            </select> 
            
            <div class="row">
                
                <CardComp v-for="(elem, index) in filterAlbums" :key="index" :card="elem"/>

            </div>
        </div>
    </div>
</template>

<script>

    
    import CardComp from './CardComp.vue'

    export default {
        name: 'AlbumList',
        components:{
            CardComp,
        },

        props:{
            albums: Array
            
        },

        data(){
            return{
                filterAlbums: [],
                arrayGeneri:[],
                genere:''

            }
        },
        
        methods:{

            getGeneri(){
                this.albums.forEach((elem) => {
                   
                    if(!this.arrayGeneri.includes(elem.genre)){
                        this.arrayGeneri.push(elem.genre)
                    }
                })
                console.log(this.arrayGeneri)

            },

            filtro(){
                if( this.genere == '' || this.genere == 'All'){
                    this.filterAlbums = this.albums
                }else{
                    this.filterAlbums=[],
                    console.log(this.genere)
                    this.albums.forEach((elem) =>{
                    
                    if( elem.genre == this.genere){
                        this.filterAlbums.push(elem)

                    }
                })
                }
                
                console.log(this.filterAlbums)
                
            }


        },

        mounted(){
            setTimeout(this.getGeneri, 1000)
            setTimeout(this.filtro, 1000)
            
        }

    }

    
</script>

<style lang="scss" scoped>
    .row{
        flex-wrap: wrap;
    }
</style>