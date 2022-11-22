<template>
    <section id="blog">
        <div class="container">
            <div class="box">
                <div class="row">
                   <!-- <BlogPost v-for="(item,index) in posts" :key="index" :obj="item"/> -->
                    <div class="card">
                        <div class="date">
                            <div class="day font-italic">07</div>
                            <div class="year">May ' 19'</div>
                        </div>
                        <div class="img-cont">
                            <img src="../assets/images/h-2-blog-img-1.jpg" alt="">   
                        </div>
                        <h4><span>This way, loves: a detailed guide through new design</span></h4>
                        <div class="credits font-italic">by Emily Fields</div>
                    </div>   
                    <div class="card">
                        <div class="date">
                            <div class="day font-italic">07</div>
                            <div class="year">May ' 19'</div>
                        </div>
                        <div class="img-cont">
                            <img src="../assets/images/h-2-blog-img-2.jpg" alt="">   
                        </div>
                        <h4><span>I try to give people a different way of looking art</span></h4>
                        <div class="credits font-italic">by Emily Fields</div>
                    </div> 
                    <div class="card">
                        <div class="date">
                            <div class="day font-italic">07</div>
                            <div class="year">May ' 19'</div>
                        </div>
                        <div class="img-cont">
                            <img src="../assets/images/h-2-blog-img-3.jpg" alt="">   
                        </div>
                        <h4><span>Introduce Richard Laperrière of those amazing features</span></h4>
                        <div class="credits font-italic">by Emily Fields</div>
                    </div>     
                </div>
            </div>
        </div>
    </section>
</template>

<script>
// import {blogPosts} from '../data/arrays'
// import BlogPost from './BlogPost.vue';

    export default {
    name: "AppBlog",
    // components: { BlogPost },
    // data(){
    //     return {
    //         posts: blogPosts,
    //     }
    // }
}
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables' as *;
@use '../assets/styles/partials/mixins' as *;

.box{
    width: 100%;

    .row{
        width: 100%;
        @include dflex-center;

        .card{
        flex-basis: calc(100% / 3);
        padding: 0 .85rem;
        position: relative;
            .date{
                height: 70px;
                width: 65px;
                background-color: $bg-color-mint;
                position: absolute;
                top: -1rem;
                left: 1.8rem;
                z-index: 1;
                .day{
                    font-size: 2rem;
                    text-align: center;
                    margin-top: -.35rem;
                }
                .year{
                    font-size: .55rem;
                    font-weight: 700;
                    text-align: center;
                    text-transform: uppercase;
                    padding-top: .55rem;
                }
            }
            .img-cont{
                overflow: hidden;
                height: 300px;


                img{
                    transition: transform 450ms ease;
                    
                }

                img:hover{
                    transform: scale(1.05);
                }
            }
           h4{
                max-width: 100%;
                font-size: 1.5rem;
                font-weight: 400;
                margin: 1rem 0;
                padding-top: .75rem;
                cursor: pointer;
            span{
               
                width: 100%;
                background-image: linear-gradient(to bottom,
                 rgba(192,255,207,0) 60%,
                 rgba(192,255,207,.5) 40%,
                 );
                 background-size: 0 100%;
                 background-repeat: no-repeat;
                 transition: 450ms linear;
            }
            span:hover{
                background-size: 100% 100%;
            }

           }
           
            // h4{
            //     font-weight: 400;
            //     font-size: 1.5rem;
            //     margin: 1rem 0;
            //     display: inline-block;
            //     position: relative;

            //     &:hover{
            //         text-decoration: line-through;
            //     }
            // }
            // h4::after{
            //     content: '';
            //     display: block;
            //     width: 0%;
            //     height: 12px;
            //     background: rgba($color: $bg-color-mint, $alpha: .5);
            //     position: absolute;
            //     bottom: 0;
            //     z-index: -1;

            //     -webkit-transition: width 1s;
            //     -moz-transition: width 1s;
            //     -o-transition: width 1s;
            //     transition: width 1s;

            // }           
            // h4:hover::after{
            //     width: 100%;
            // } 
           

            .credits{
                font-size: 1rem;
                font-weight: 200;
            }
    }

    }
}
</style>