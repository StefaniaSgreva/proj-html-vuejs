<template>
    <section id="hero">
        <button class="handle left-handle" @click="prev()"><i class="fa-solid fa-chevron-left"></i></button>
        <div class="hero-container">
            <div class="carousel" ref="scroll" v-for="(slide, index) in slides" :key="index" 
                :current-slide="currentSlide" :index="index" :direction="direction"
                @mouseenter="stopSlideTimer" @mouseout="startsSlideTimer">
                <transition :name="transitionEffect">
                    <div class="carousel-item"  v-show="currentSlide === index">
                        <div class="text">
                            <h1>{{slide.title1}}<br>{{slide.title2}} <span class="font-italic">{{slide.titleItalic}}</span></h1>
                            <p>{{slide.text}}</p>
                        <button class="btn prova">Read More</button>
                        </div>
                        <div class="img">
                            <img :src="slide.image" alt="hero slide">
                        </div>
                    </div>
                </transition>
            </div>
            
            <!-- <div class="btn-position" >
                <button class="btn prova">Read More</button>
            </div> -->
            
            <div class="carousel-indicators">
                <button class="carousel-indicator-item" 
                v-for="(item,index) in slides.length" :key="index"
                :class="{active: currentSlide === index}" @click="switchSlide(index)"></button>
            </div>
        </div>
        <button class="handle right-handle" @click="next()"><i class="fa-solid fa-chevron-right"></i></button>

    </section>
</template>

<script>
    export default {
        name: 'AppHero',
        data(){
            return{
                currentSlide: 0,
                slideInterval: null,
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
                ],
                direction: "right",
                
            }
        },
        methods:{
            setCurrentSlide(index){

                this.currentSlide = index;
            },
            prev(step = -1){
                const index = this.currentSlide > 0 ? this.currentSlide + step : this.slides.length -1;
                this.setCurrentSlide(index);
                this.direction = "left";
                this.startsSlideTimer();
            },
            _next(step = 1){
                const index =
                this.currentSlide < this.slides.length - 1 ? this.currentSlide + step : 0;
                this.setCurrentSlide(index);
                this.direction = "right";
            },
            next(step = 1){
                this._next(step);
                this.startsSlideTimer();
            },
            startsSlideTimer(){
                this.stopSlideTimer();
                this.slideInterval = setInterval(()=>{

                    this._next();

                }, 5000);
            },
            stopSlideTimer(){
                clearInterval(this.slideInterval);
            },
            switchSlide(index){
                const step = index - this.currentSlide;
                if(step > 0){
                    this.next(step);
                }else{
                    this.prev(step);
                }
            }
          

        },
        computed:{
            transitionEffect(){
                return this.direction === "right" ? "slide-out" : "slide-in";
            }
        },
        mounted(){
            this.startsSlideTimer();
        },
        beforeUnmount(){
            this.stopSlideTimer();
        }
    }
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables' as *;
@use '../assets/styles/partials/mixins' as *;

#hero{
    margin: 2rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.hero-container{
    display: flex;
    justify-content: center;
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
                // border: 2px solid green;
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
                    
            }

            .img{
                width: 50%;
                // border: 2px solid blue;
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
.carousel-indicators{
    position: absolute;
    bottom: 0;
    left: 47%;

    .carousel-indicator-item{
        width: 12px;
        height: 12px;
        border-radius: 50%;
        background-color: $bg-color-pink;
        border: none;
        margin: .45rem;
        cursor: pointer;
    }
    .active{
        background-color: $bg-color-mint;
    }

}
.slide-in-enter-active,
.slide-in-leave-active,
.slide-out-enter-active,
.slide-out-leave-active{
    transition: all 1s ease-in-out;
}
.slide-in-enter-from{
    transform: translateX(-100%);
}
.slide-in-leave-to{
    transform: translateX(100%);
}
.slide-out-enter-from{
    transform: translateX(100%);
}
.slide-out-leave-to{
    transform: translateX(-100%);
}
.btn-position{
    position: absolute;
    left: 0;
    bottom: 4rem;
}
.prova{
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
.prova::after{
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
.prova:hover::after{
    transform: scaleX(1);
    transform-origin: left;

}
    

</style>