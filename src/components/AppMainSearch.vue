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
    gap: 10px;
    padding: 20px;
    height: 70px;
    
    input{
        outline: none;
        border: 1px solid transparent;
        border-radius: 5px;
    }
}

</style>