<template>
    <section id="call-to-action">
        <h2>Want to work with us? Send us <span class="font-italic">a message!</span></h2>
        <p>Lorem ipsum dolor sit amet, consectetur elit, sed do eiusmod tempor incididunt ut labore et dolore. Ut enim ad minim veniam, quis nostrud exercitatian ullamco laboris nisi ut aliquip ex ea commo.</p>
        <button class="btn">Contact</button>
    </section>
</template>

<script>
    export default {
        name: 'CallToAction'
    }
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables' as *;
@use '../assets/styles/partials/mixins' as *;

#call-to-action{
    width: 100%;
    height: 450px;
    background-image: url(../assets/images/h-2-background-1.jpg);
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
    text-align: center;
    @include dflex-center-col;

   
    p{
        width: 1200px;
        line-height: 2rem;
        color: $text-color-gray;
        padding: 1.5rem 0;
    }
    button{
        padding: .85rem 2.8rem;
        background-color: rgba($color: #c0e1cf, $alpha: 0.6);
        
        
    }
}

</style>