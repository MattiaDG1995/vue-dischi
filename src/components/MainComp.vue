<template>
    <div class="container">
        <AlbumList :albums="arrayAlbums" />
    </div>
</template>

<script>
import axios from 'axios'
import AlbumList from './AlbumList.vue'

    export default {
        name: 'MainComp',
        
        components:{
            AlbumList

        },
        data(){
            return{
                arrayGeneri:[],
                arrayAlbums: []
            }
        },
        methods:{

            listaAlbums(){
                axios.get('https://flynn.boolean.careers/exercises/api/array/music')
                .then(res=>{
                    this.arrayAlbums = res.data.response;
                   /*  console.log(this.arrayAlbums) */
                })
                
            }
        },

        mounted(){

            this.listaAlbums()
        }
        
    }
</script>

<style lang="scss" scoped>
    
</style>