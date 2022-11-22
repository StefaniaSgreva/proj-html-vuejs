<template>
    <section id="blog">
        <div class="container">
            <div class="box">
                <div class="row">
                   <BlogPost v-for="(item,index) in posts" :key="index" :obj="item"/>
                    <!-- <div class="card">
                        <div class="date">
                            <div class="day font-italic">07</div>
                            <div class="year">May ' 19'</div>
                        </div>
                        <img src="../assets/images/h-2-blog-img-1.jpg" alt="">
                        <h3>This way, loves: a detailed guide through new design</h3>
                        <div class="credits font-italic">by Emily Fields</div>
                    </div> -->       
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import {blogPosts} from '../data/arrays'
import BlogPost from './BlogPost.vue';

    export default {
    name: "AppBlog",
    components: { BlogPost },
    data(){
        return {
            posts: blogPosts,
        }
    }
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

    }
}
</style>