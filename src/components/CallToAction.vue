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
    height: 610px;
    background-image: url(../assets/images/h-2-background-1.jpg);
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
    text-align: center;
    @include dflex-center-col;

   
    p{
        width: 95%;
        font-size: 1.25rem;
        line-height: 2rem;
        color: $text-color-gray;
        padding-top: 1.5rem;
        padding-bottom: 2rem;
    }
    button{
        padding: 1.2rem 4rem;
        background-color: rgba($color: #f77b72, $alpha: 0.6);
        cursor: pointer;
        position: relative;
      

        &:hover{
            color: $color-white;
            background-color: $bg-color-pink;

        }
    }
    // button::after{
    //     content: '';
    //     position: absolute;
    //     top: 0;
    //     left: 0;
    //     width: 100%;
    //     height: 100%;
    //     background-color: rgba($color: #f3d0c7, $alpha: 0.6);
    //     transform: scaleX(0);
    //     transform-origin: right;
    //     transition: transform 200ms ease-in;
    //     z-index: -1;
    // }
    // button:hover::after{
    //     transform: scaleX(1);
    //     transform-origin: left;
    // }
    
}

</style>