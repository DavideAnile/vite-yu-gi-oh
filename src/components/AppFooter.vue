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
    <div class="footer">

        <div>
            <div class="boh"> Su questa pagina potrai visualizzare {{ store.cards.length }} card stilizzate a mano</div>
            <div class="io">contattami se anche tu vuoi uno schiavo che crea template di card  <i class="fa-solid fa-heart"></i><br>Le card ovviamente saranno bellissime!!!</div>
            <div class="p-s"><em>( Ho notato che la carta era già creata per bene in una proprietà ma ho provato a replicarla da 0, ma come vedete i risultati sono scarsi <i class="fa-solid fa-face-grin-wink"></i> )</em></div>
        </div>

        <div class="links">
            <i class="fa-brands fa-facebook"></i>
            <i class="fa-brands fa-twitter"></i>
            <i class="fa-brands fa-whatsapp"></i>
            <i class="fa-brands fa-pinterest"></i>
            <i class="fa-brands fa-instagram"></i>
        </div>

    </div>
</template>

<style lang="scss" scoped>

.footer{
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 200px;
    background-color: rgba(0, 0, 0, 0.4);
    padding: 0 50px;

    .boh{
        font-weight: bold;
        padding: 10px;
    }
    .io{
        text-transform: uppercase;
        padding: 10px;
    }

    .p-s{
        font-size: .8em;
    }
    .links{
        display: flex;
        gap: 20px;


        i{
            font-size: 2em;
            opacity: 0.5;
            transition: .5s;

            &:hover{
                opacity: 1;
                transform: scale(1.2);
                cursor: pointer;
            }
        }
    }
}


        

</style>