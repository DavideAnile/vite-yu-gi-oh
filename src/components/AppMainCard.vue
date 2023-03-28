<script>

 export default {
    data(){
        return{

        }
    },

    props : {

        card : Object,
    },
    
    methods : {
        cardType(){

            if(this.card.frameType == 'spell'){
                return 'spell'
            } else if ( this.card.frameType == 'trap'){
                return 'trap'
            } else if (this.card.frameType == 'effect'){
                return 'effect'
            } else {
                return 'fusion'
            }

        }
    }

 }
</script>

<template>
    
        
        <div class="card" :class="cardType()">
            
            <div class="title">{{ card.name }}</div>
            <div class="image">
                <img :src=card.card_images[0].image_url_cropped alt="">
            </div>
            <div class="desc" :class="cardType()">{{ card.desc }}</div>
        </div>
       
        
   



</template>

<style lang="scss" scoped>


    
   .card{
    
    width: 300px;
    height: 450px;
    background-color: #4c2f29;
    border: 8px solid rgba(0, 0, 0, 0.753);
    margin: 40px 0;
    transition: .5s
    
;

    .title{
        display: flex;
        align-items: center;
        width: 90%;
        height: 8%;
        border-top: 2px solid rgba(255, 255, 255, 0.541);
        border-right: 2px solid rgba(0, 0, 0, 0.493);
        border-bottom: 2px solid rgba(0, 0, 0, 0.548);
        border-left: 2px solid rgba(255, 255, 255, 0.514);
        margin: 10px auto;
        white-space: nowrap;
        font-family: serif;
        font-size: .7em;
        font-weight: bold;
        padding: 2px;
        color: white;
        text-transform: uppercase;
        
       
        
        
        
    }
        
    .image{
        width: 75%;
        height: 62%;
        border: 4px solid rgba(0, 0, 0, 0.568);
        margin: 10px auto;

        img{
            height: 100%;
            width: 100%;
            object-fit: cover;
            object-position: top;
        }
        
    }    

    .desc{
        display: flex;
        align-items: flex-start;
        width: 80%;
        height: 20%;
        border: 2px solid #a74e26;
        margin: 0 auto;
        font-size: .6em;
        padding: 3px;
        overflow-y: hidden;
        color: black;
        
        
            
        &.spell{
            background-color: #a5d1cc;
        }

        &.trap{
            background-color: #fdd0e5;
        }

        &.effect{
            background-color:#d9b18a;
        }

        &.fusion{
            background-color: #baaec7;
        }
        
        
    }

    &:hover{
        cursor: pointer;
        transform: scale(1.1);
    }

   }

   .spell{
    background-color: #53b6ab;
   }

   .trap{
    background-color: #8f0d6d;
   }

   .effect{
    background-color: #5f2619;
   }

   .fusion{
    background-color: #59208f;
   }
   


</style>