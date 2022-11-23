<template>
   <header>
            <a href="#">
                <img src="../assets/images/logo-sidearea-1.png" alt="logo" class="header-logo">
            </a>
        <nav>
            <ul>
                <li v-for="(link,index) in headerNav" :key="index">
                    <a href="link.url" :class="{'active' : link.current}" class="strike">{{link.text}}</a>    
                </li>
                <li><a href="#"><img src="../assets/svg/svg-1.svg" alt="menu"></a></li>
            </ul>
        </nav>
       
   </header>
</template>

<script>
import {headerLinks} from '../data/arrays'
    export default {
        name: 'AppHeader',
        data(){
            return{
                headerNav: headerLinks
            }
        }
    }
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables' as *;
@use '../assets/styles/partials/mixins' as *;

header{
    width: 95%;
    margin: 0 auto;
    height: 60px;
    @include dflex-between;
    padding-top: 2.5rem;

    ul{
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: .85rem;
        font-weight: 700;


        
            li a{
                text-transform: uppercase;
                margin-left: 3rem;
                letter-spacing: .10rem;
                display: inline-block;
                position: relative;
            }
            .strike::after{
                content: '';
                display: block;
                width: 0%;
                height: 6px;
                background: $bg-color-pink;
                position: absolute;
                bottom: 0;
                z-index: -1;
                transition: 400ms ease-in-out;
            }           
            .strike:hover::after{
                content: '';
                display: block;
                width: 100%;
                height: 6px;
                background: $bg-color-pink;
                position: absolute;
                bottom: 0;
                z-index: -1;
            } 
            .strike.active::after{
                width: 100%;
            }
            // a img{
            //     transition: transform 450ms ease;
            // }
            // a img:hover{
            //     transform: scale(1.1);
                
            // }
    }

}
</style>