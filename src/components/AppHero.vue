<template>
    <section id="hero">
        <div class="hero-container debug">
            <button class="handle left-handle" @click="scrollLeft()"><i class="fa-solid fa-chevron-left"></i></button>
            <div class="carousel" ref="scroll" v-for="(slide, index) in slides" :key="index" 
                :current-slide="currentSlide" :index="index">
                <div class="carousel-item"  v-show="currentSlide === index">
                    <div class="text">
                        <h1>{{slide.title1}}<br>{{slide.title2}} <span class="font-italic">{{slide.titleItalic}}</span></h1>
                        <p>{{slide.text}}</p>
                        <button class="btn">Read More</button>
                    </div>
                    <div class="img">
                        <img :src="slide.image" alt="hero slide">
                    </div>
                </div>
            </div>
            <div class="dots">
                <div class="dot"></div>
                <div class="dot"></div>
                <div class="dot"></div>
            </div>
            <button class="handle right-handle" @click="scrollRight()"><i class="fa-solid fa-chevron-right"></i></button>
        </div>
    </section>
</template>

<script>
    export default {
        name: 'AppHero',
        data(){
            return{
                currentSlide: 0,
                slides:[
                    {
                        image: '/img/Hero-imh-1.png',
                        title1: 'Devotion that',
                        title2: 'never',
                        titleItalic: 'ends',
                        text: 'Neque porro quisquam est, qui dolorem ipsum quoia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi'
                    },
                    {
                        image: '/img/Hero-imh-1.png',
                        title1: 'Projects made',
                        title2: 'with',
                        titleItalic: 'love',
                        text: 'Neque porro quisquam est, qui dolorem ipsum quoia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi'
                    },
                    {
                        image: '/img/Hero-imh-1.png',
                        title1: 'Our new folio',
                        title2: 'full of',
                        titleItalic: 'joy',
                        text: 'Neque porro quisquam est, qui dolorem ipsum quoia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi'
                    }
                ]
            }
        },
        methods:{
            scrollLeft(){
                this.$refs['scroll'].scrollLeft -= 1000;
            },
            scrollRight() {
                this.$refs['scroll'].scrollLeft += 1000;
            }

        },
        mounted(){
            
        }
    }
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables' as *;
@use '../assets/styles/partials/mixins' as *;

#hero{
    margin: 2rem 0;
}
.hero-container{
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: relative;
    width: 90%;
    margin: 0 auto;
    height: 520px;
    overflow: hidden;
    position: relative;
   

    .carousel{
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;

        .carousel-item{
            display: flex;
            justify-content: flex-end;
            align-items: center;
            height: 100%;
           


            .text{
                width: 50%;
                border: 2px solid green;
                height: 100%;
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: flex-start;

                    h1{
                        font-size: 4.5rem;
                        font-weight: 300;
                        line-height: 4.5rem;
                    }

                    p{
                        color: $text-color-gray;
                        line-height: 1.8rem;
                        margin: 1.8rem 0;
                        font-size: 1.2rem;
                        max-width: 580px;
                    }
                    button{
                        margin-top: .55rem;
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
                width: 50%;
                border: 2px solid blue;
                height: 100%;
                display: flex;
                justify-content: center;
                align-items: center;

                img{
                    width: 100%;
                }

            }

        }
    }
}
.handle{
    cursor: pointer;
}
.dots{
    position: absolute;
    bottom: 0;
    left: 47%;
    display: flex;
    .dot{
        width: 10px;
        height: 10px;
        border-radius: 50%;
        background-color: $bg-color-pink;
        margin-right: 1.5rem;
        cursor: pointer;
    }
}

    

</style>