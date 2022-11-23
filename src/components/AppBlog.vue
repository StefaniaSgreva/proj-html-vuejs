<template>
    <section id="blog">
        <div class="container">
            <div class="box">
                <div class="row">
                   <BlogPost v-for="(item,index) in posts" :key="index" :obj="item"/>
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

#blog{
    padding: 4.5rem 0;
}
.box{
    width: 100%;
    .row{
        width: 100%;
        @include dflex-center;    
    }
}
</style>