<script>
import AppMainCard from "./AppMainCard.vue"
import AppMainSearch from "./AppMainSearch.vue"


import axios from "axios"
import {store} from "../store.js"


 export default {
    data(){
        return{

            store,
        }
    },

    created(){
        axios.get(this.store.apiCall).then((res) => {
            this.store.cards = res.data.data
            
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
                
                this.store.cards = res.data.data
            })
        }
    }
 }
</script>

<template>
    <section>

        <AppMainSearch @searchCard="search()"></AppMainSearch>

        <div class="container">
            
            <AppMainCard v-for="card in store.cards" :card="card"></AppMainCard>
    
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
    
    
}

</style>