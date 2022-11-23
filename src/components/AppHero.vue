<template>
    <section id="hero">
        <div class="hero-container debug">
            <button class="handle left-handle"><i class="fa-solid fa-chevron-left"></i></button>
            <div class="slide">
                <div class="text">
                    <h1>Devotion that<br>never <span class="font-italic">ends</span></h1>
                    <p>Neque porro quisquam est, qui dolorem ipsum quoia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi</p>
                    <button class="btn">Read More</button>
                </div>
                <div class="img debug">
                    <img src="../assets/images/Hero-imh-1.png" alt="">
                </div>
              
                <div class="dots">
                    <div class="dot"></div>
                    <div class="dot"></div>
                    <div class="dot"></div>
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
            width: 90%;
            height: 425px;
            margin: 5rem 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
            
           
            .left-handle{
                position: absolute;
                left: 0;
                top: 42%;
            }
            .right-handle{
                position: absolute;
                right: 0;
                top: 42%;
            }

            .slide{
                display: flex;
                // flex-wrap: wrap;
                justify-content: flex-end;
                align-items: center;
                height: 100%;
                position: relative;
                .text{
                    width: 50%;
                    height: 100%;
                    // border: 1px solid red;
                    display: flex;
                    flex-direction: column;
                    align-items: flex-start;
                    justify-content: center;
                    padding-top: 1rem;

                    h1{
                        font-size: 4.5rem;
                        font-weight: 300;
                        line-height: 4rem;
                    }

                    p{
                        color: $text-color-gray;
                        line-height: 1.5rem;
                        margin: 1.5rem 0;
                        font-size: 1.2rem;
                    }
                    button{
                        margin-top: 1rem;
                        padding: 1.25rem 2.2rem;
                        background-color: transparent;
                        border: 3px solid $border-color-pink;
                        cursor: pointer;
                        position: relative;
                        font-size: .85rem;

                        &:hover{
                            color: $color-white;
                        }

                    }
                    button::after{
                        content: '';
                        position: absolute;
                        top: 0;
                        left: 0;
                        width: 100%;
                        height: 100%;
                        background: $border-color-pink;
                        transform: scaleX(0);
                        transform-origin: right;
                        transition: transform 200ms ease-in;
                        z-index: -1;


                    }
                    button:hover::after{
                        transform: scaleX(1);
                        transform-origin: left;

                    }

                }
                .img{
                    // border: 1px solid red;
                    width: 50%;
                    height: 100%;
                    display: flex;
                    justify-content: center;
                    align-items: center;  

                    img{
                        transform: scale(1.3);
                        padding-left: 2rem;
                    }
                }
                .dots{
                    // border: 1px solid red;
                    position: absolute;
                    bottom: -3rem;
                    left: 40%;
                    display: flex;
                }
                .dot{
                        width: 10px;
                        height: 10px;
                        border-radius: 50%;
                        background-color: $bg-color-pink;
                        margin-right: 1.5rem;
                   }
            }
           
        }
    }

</style>