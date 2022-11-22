<template>
    <div class="card">
        <div class="date">
            <div class="day font-italic">07</div>
            <div class="year">May ' 19'</div>
        </div>
        <img :src="getImageURL(`h-2-blog-img-1.jpg`)" alt="blog post image">
        <!-- <img :src="`/images/${ obj.imageName }.jpeg`" alt="blog post image"> -->
        <h3>{{obj.title}}</h3>
        <div class="credits font-italic">{{obj.credits}}</div>
    </div>
</template>

<script>
    export default {
        name: 'BlogPost',
        props:[
           
            'obj'
        ],
        methods:{
            getImageURL: function (imgPath) {
                return new URL(`../assets/images/${imgPath}`, import.meta.url).href;
                }           

        }
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
                width: 60px;
                background-color: red;
                position: absolute;
                top: -1rem;
                left: 1.8rem;

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

            h3{
                font-weight: 400;
                font-size: 1.3rem;
                margin: 1rem 0;
            }

            .credits{
                font-size: .85rem;
                font-weight: 500;
            }
    }
</style>