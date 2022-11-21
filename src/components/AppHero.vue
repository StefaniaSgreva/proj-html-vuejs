<template>
    <section id="hero">
        <div class="hero-container">
            <button class="handle left-handle"><i class="fa-solid fa-chevron-left"></i></button>
            <div class="slide">
                <div class="text">
                <h1>Devotion that<br>never <span class="font-italic">ends</span></h1>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima quis cupiditate</p>
                    <button class="btn">Read More</button>
                </div>
                <div class="img">
                    <!-- <img src="../assets/images/h-2-slider-img-12.png" alt="">
                    <img src="../assets/images/h-2-slider-img-13.png" alt="">
                    <img src="../assets/images/h-2-slider-img-14.png" alt="">
                    <img src="../assets/images/h-2-slider-img-17.png" alt="">
                    <img src="../assets/images/short-slider-rev-1-img-2.png" alt="">
                    <img src="../assets/images/short-slider-rev-1-img-6.png" alt=""> -->

                    <div class="characters">
                        <img src="../assets/images/h-2-slider-img-15.png" alt="">
                        <img src="../assets/images/h-2-slider-img-16.png" alt="">
                    </div>
                </div>
            </div>
            <button class="handle right-handle"><i class="fa-solid fa-chevron-right"></i></button>
        </div>

    </section>
</template>

<script>
    export default {
        name: 'AppHero'
    }
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables' as *;
@use '../assets/styles/partials/mixins' as *;

    #hero{
        display: flex;
        justify-content: flex-end;
        position: relative;
        margin: 0 2rem;
        .hero-container{
            width: 80%;
            height: 420px;
            margin: 5rem 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
            
           
            .left-handle{
                position: absolute;
                left: 0;
                top: 45%;
            }
            .right-handle{
                position: absolute;
                right: 0;
                top: 45%;

            }

            .slide{
                display: flex;
                justify-content: flex-end;
                align-items: center;
                height: 100%;
                .text{
                width: 40%;
                height: 100%;
                border: 1px solid red;
                display: flex;
                flex-direction: column;
                align-items: flex-start;
                justify-content: flex-start;
                padding-top: 1rem;

                h1{
                    font-size: 4rem;
                    font-weight: 400;
                    line-height: 3.5rem;
                }

                p{
                    color: $text-color-gray;
                    line-height: 1.5rem;
                    margin: 2rem 0;
                }
                button{
                    padding: 1rem 2rem;
                    background-color: transparent;
                    border: 3px solid $border-color-pink;
                }

                }
                .img{
                    border: 1px solid red;
                    width: 60%;
                    height: 100%;
                    display: flex;
                    justify-content: center;
                    align-items: center;

                    .characters{
                        display: flex;

                        img{
                            width: 40%;
                            margin: 0 auto;
                        }
                    }
                    
                }
            }
           
        }
    }

</style>