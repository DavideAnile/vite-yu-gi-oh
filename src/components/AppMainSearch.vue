<script>
import { store } from '../store.js';

    export default{
        data(){
            return{

               store, 

            }
        }
    }

</script>

<template>
    <div class="search-container">
        <input type="text" placeholder="Cerca una carta..." v-model="store.cardName" @keyup.enter="$emit('searchCard')">
        <button @click="$emit('searchCard')">CERCA</button>
    </div>
</template>

<style lang="scss" scoped>

.search-container{
    display: flex;
    flex-flow: row;
    justify-content: center;
    align-items: center;
    gap: 10px;
    padding: 20px;
    height: 70px;
    
    background-color: rgba(255, 255, 255, 0.253);
    
    input{
        width: 15%;
        outline: none;
        border: 1px solid transparent;
        border-radius: 5px;
        padding: 8px 20px;
    }

    button{
        padding: 5px;
    }
}

</style>