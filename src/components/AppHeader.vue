<template>
   <header>
            <a href="#">
                <img src="../assets/images/logo-sidearea-1.png" alt="logo" class="header-logo">
            </a>
        <nav>
            <ul>
                <li v-for="(link,index) in headerNav" :key="index">
                    <a href="link.url" :class="{'active' : link.current}">{{link.text}}</a>    
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
    padding-top: 2rem;

    ul{
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: .85rem;
        font-weight: 600;


        
            li a{
                text-transform: uppercase;
                margin-left: 2.5rem;
                letter-spacing: .10rem;
                // border: 1px solid red;
             

                &.active,
                &:hover{
                    // border: 1px solid red;
                    // border-bottom: 4px solid $bg-color-pink;
                    // padding: 0 3px;
                    border-bottom-width:0.4em;
                    border-bottom-style:solid;
                    border-bottom-color:$bg-color-pink;
                }
            }      
    }

}
</style>