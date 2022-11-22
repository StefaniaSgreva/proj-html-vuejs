<template>
    <footer>
        <div class="container">
            <div class="logo">
            <img src="../assets/images/logo-sidearea-1.png" alt="logo">
                <div>Let's Get Creative</div>
            </div>
            <FooterInfos v-for="(menu,index) in footerList" :key="index" :item="menu"/>
            <div class="social-links">
                <div>Stay in touch with us</div> 
                <div>
                    <a href="#"><i class="fa-brands fa-twitter"></i></a>
                    <a href="#"><i class="fa-brands fa-pinterest-p"></i></a>
                    <a href="#"><i class="fa-brands fa-facebook-f"></i></a>
                    <a href="#"><i class="fa-brands fa-linkedin-in"></i></a>
                </div>
            </div>
        </div>
        
    </footer>
</template>

<script>
import {footerMenu} from '../data/arrays';
import FooterInfos from './FooterInfos.vue';
    export default {
        name: 'AppFooter',
        components: {FooterInfos},
        data(){
            return{
                footerList: footerMenu,
            }
        }
    }
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables' as *;
@use '../assets/styles/partials/mixins' as *;

footer{
    background-color: $bg-color-mint;
    width: 100%;
    padding-top: 3rem;
    padding-bottom: 4rem;
    // position: fixed;
    // bottom: 0;
  
    .container{
        display: flex;
        justify-content: flex-start;
        align-items: center;
        font-size: .85rem;
        // border: 1px solid red;
        .logo{
            line-height: 1.6rem;
            margin-right: 9rem;
        }

        .social-links{
            text-align: center;
            line-height: 2rem;

            div{
                font-size: .95rem;
            }
            
            div:nth-child(2){
            padding-left: 2rem;
            }

            i{
                color: $text-color;
                padding-right: 1.8rem;
                font-size: 1rem;
                transition: color 450ms ease;
            }
            i:hover{
                color: $color-white;
            }
        }
    }

    
}
</style>