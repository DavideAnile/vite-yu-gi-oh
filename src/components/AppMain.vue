<script>
import AppMainCard from "./AppMainCard.vue"
import AppMainSearch from "./AppMainSearch.vue"


import axios from "axios"
import {store} from "../store.js"


 export default {
    data(){
        return{

            store,

            isLoading : true
        }
    },

    created(){
        axios.get(this.store.apiCall).then((res) => {
            this.store.cards = res.data.data;

            this.isLoading = false
            
        })
            


    },

    components : {
        AppMainCard,
        AppMainSearch
    },

    methods : {
        search(){
            
            let newApiCall = (this.store.apiCall + this.store.apiQuery + this.store.cardName)

            axios.get(newApiCall).then((res) =>{
               
                this.store.cardFound = true
                this.store.cards = res.data.data
                this.store.cardName = ''

            }).catch((err) => {

                this.store.cardFound = false
                this.store.cardName = ''
            })

            
        }
    }
 }
</script>

<template>
    <section>

        <AppMainSearch @searchCard="search()"></AppMainSearch>
        
        <div class="loading" v-if="isLoading">Caricamento delle carte...</div>

        <div class="container" v-else>
            
            <div v-if="this.store.cardFound == false " class="not-found">Nessuna carta trovata</div>
            <AppMainCard v-else v-for="card in store.cards" :card="card"></AppMainCard>
        </div>

    </section>
</template>

<style lang="scss" scoped>

section{
    background: linear-gradient(0.25turn, #552635, #948981, #52389b);
    
    
    
}
.container{
    
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    gap: 40px;
    width: 1500px;
    margin:  auto;

    .not-found{
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100vw;
        height: 100vh;
        text-transform: uppercase;
        font-weight: bold;
    }

}
    
.loading{
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100vw;
        height: 100vh;
        text-transform: uppercase;
    }    
    

</style>