<template>
    <section id="portfolio">
        <div class="port-container">
            <div class="col">
                <img src="../assets/images/h-2-port-img-1.jpg" alt="">
                <img src="../assets/images/h-2-port-img-2.jpg" alt="">
                <img src="../assets/images/h-2-port-img-3.jpg" alt="">
            </div>
            <div class="col">
                <img src="../assets/images/h-2-port-img-4.jpg" alt="">
                <img src="../assets/images/h-2-port-img-5.jpg" alt="">
                <img src="../assets/images/h-2-port-img-6.jpg" alt="">
            </div>
        </div>
    </section>
</template>

<script>
    export default {
        name: 'AppPortfolio'
    }
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables' as *;
@use '../assets/styles/partials/mixins' as *;

    #portfolio{
        width: 100%;
        
        .port-container{
         width: 100%;

           .col{
            width: calc(100% / 3);
            display: flex;
           }
        }
    }
</style>