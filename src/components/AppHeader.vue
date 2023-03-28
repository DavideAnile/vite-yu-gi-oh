<script>
    export default{
        data(){
            return{
                links: [
                    'gioca',
                    'prodotti',
                    'novità',
                    'eventi',
                ]
                
                
            }
        }
    }

</script>

<template>
<div id="header">
    <div class="logo">
        <img src="/images/yugioh-logo.svg" alt="">
    </div>
    <div class="links">
        <ul>
            <li v-for="link in links"> {{ link }}</li>
            
        </ul>
    </div>
    
</div>
</template>

<style lang="scss" scoped>

#header{
    display: flex;
    justify-content: space-around;
    align-items: center;
    padding: 10px;
    height: 100px;
    background-color: rgba(0, 0, 0, 0.4);

    .logo{
        height: 100%;
        

        img{
            height: 100%;
        }
    }

    .links{
        height: 100%;

        ul{
            display: flex;
            gap: 20px;
            height: 100%;
            font-weight: bold;
            list-style-type: none ;
            text-transform: uppercase;

            li{
                display: flex;
                align-items: center;
                height: 100%;
                padding: 5px;
                border: 1px solid transparent;
                border-radius: 10px;

                &:hover{
                    background-color: red;
                    cursor: pointer;
                }
            }
        }
    }
}

</style>