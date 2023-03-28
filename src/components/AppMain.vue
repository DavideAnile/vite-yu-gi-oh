<script>
import axios from "axios"
import {store} from "../store.js"

import AppMainCard from "./AppMainCard.vue"

 export default {
    data(){
        return{

            store,
        }
    },

    created(){
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0').then((res) => {
            this.store.cards = res.data.data
            console.log(store.cards)
        })

    },

    components : {
        AppMainCard,
    }
 }
</script>

<template>
    <section>
        <div class="container">
            
            <AppMainCard v-for="card in store.cards" :card="card"></AppMainCard>
    
        </div>

    </section>
</template>

<style lang="scss" scoped>

section{
    background: linear-gradient(0.25turn, #094b68, #836e40, #9e2379);
    
    
    
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