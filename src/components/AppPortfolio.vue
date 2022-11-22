<template>
    <section id="portfolio">
        <div class="port-container">
            <div class="col">
                <div class="box">
                    <img src="../assets/images/h-2-port-img-1.jpg" alt="">
                    <div class="content">
                        <h4>All these illustritations</h4>
                    </div>
                    <div class="font-italic">Illustration</div>
                </div>
                <div class="box">
                    <img src="../assets/images/h-2-port-img-2.jpg" alt="">
                    <div class="content">
                        <h4>Type and illustritations</h4>
                    </div>
                    <div class="font-italic">Illustration</div>
                </div>
                <div class="box">
                    <img src="../assets/images/h-2-port-img-3.jpg" alt="">
                    <div class="content">
                        <h4>Draw and illustrate</h4>
                    </div>
                    <div class="font-italic">Illustration</div>
                </div>
            </div>
            <div class="col">
                <div class="box">
                    <img src="../assets/images/h-2-port-img-4.jpg" alt="">
                    <div class="content">
                        <h4>Illustritations of novels</h4>
                    </div>
                    <div class="font-italic">Illustration</div>
                </div>
                <div class="box">
                    <img src="../assets/images/h-2-port-img-5.jpg" alt="">
                    <div class="content">
                        <h4>Too many illustritations</h4>
                    </div>
                    <div class="font-italic">Illustration</div>
                </div>
                <div class="box">
                    <img src="../assets/images/h-2-port-img-6.jpg" alt="">
                    <div class="content">
                        <h4>Dreams are illustritations</h4>
                    </div>
                    <div class="font-italic">Illustration</div>
                </div>
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
                 @include dflex-center;
                  

                .box{
                    width: calc(100% / 3);
                    height: 665px;
                    position: relative;
                    cursor: pointer;
                    overflow: hidden;

                   img{
                    height: auto;
                   }
                   h4{
                        font-weight: 500;
                        font-size: 1.6rem;
                        padding-bottom: .55rem;
                        opacity: 0;
                        transition: 1s ease-in;

                   }
                   
                   .content{
                    background-color: $bg-color-white ;
                    padding: 1.5rem;
                    padding-bottom: 2.8rem;
                    position: absolute;
                    top: 42%;
                    left: -100%;
                    transition-duration: 0.5s;
                   }
                }
                .box:hover .content{
                     left: 0;
                }
                .font-italic{
                            font-size: 1rem;
                            font-weight: 200;
                            position: absolute;
                            top: 51%;
                            left: -100%;
                            transition-duration: 0.7s;
                            z-index: 1;
                }
                .box:hover .font-italic{
                    left: 1.5rem;
                }
                .box:hover h4{
                    opacity: 1;
                }
           }
        }
    }
</style>