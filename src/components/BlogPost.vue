<template>
    <div class="card">
        <div class="date">
            <img src="../assets/images/bandierina.png" alt="decorative flag">
            <div class="day font-italic">07</div>
            <div class="year">May ' 19'</div>
        </div>
        <!-- <img :src="getImageURL(`h-2-blog-img-1.jpg`)" alt="blog post image"> -->
        <div class="blog-img-cont">
             <img :src="obj.img" alt="blog post image">
        </div>
        <h4><span>{{obj.title}}</span></h4>
        <div class="credits font-italic">{{obj.credits}}</div>
    </div>
</template>

<script>
    export default {
        name: 'BlogPost',
        props:[
           
            'obj'
        ],
        // methods:{
        //     getImageURL: function (imgPath) {
        //         return new URL(`../assets/images/${imgPath}`, import.meta.url).href;
        //         }           

        // }
    }
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables' as *;
@use '../assets/styles/partials/mixins' as *;
    .card{
        flex-basis: calc(100% / 3);
        padding: 0 .85rem;
        position: relative;
            .date{
                height: 70px;
                width: 65px;
                // background-color: $bg-color-mint;
                position: absolute;
                top: -1rem;
                left: 1.8rem;
                z-index: 1;
                .day{
                    font-size: 2rem;
                    text-align: center;
                    margin-top: -5.2rem;
                }
                .year{
                    font-size: .55rem;
                    font-weight: 700;
                    text-align: center;
                    text-transform: uppercase;
                    padding-top: .55rem;
                }
            }
            .blog-img-cont{
                overflow: hidden;
               
                img{
                    transition: transform 450ms ease;
                    transform: scale(1.05);
                }

                img:hover{
                    transform: scale(1.1);
                }
            }

            h4{
                max-width: 500px;
                font-size: 1.5rem;
                font-weight: 400;
                margin: 1rem 0;
                padding-top: .75rem;
                cursor: pointer;
            span{
               
                width: 100%;
                background-image: linear-gradient(to bottom,
                 rgba(247,123,114,0) 60%,
                 rgba(247,123,114,.5) 40%,
                 );
                 background-size: 0 100%;
                 background-repeat: no-repeat;
                 transition: 450ms linear;
            }
            span:hover{
                background-size: 100% 100%;
            }

           }
           .credits{
                font-size: 1rem;
                font-weight: 200;
            }
    }
</style>