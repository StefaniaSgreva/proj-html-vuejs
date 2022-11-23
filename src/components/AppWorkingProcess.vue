<template>
    <section id="process">
        <div class="container">
            <h2>Working <span class="font-italic">process</span></h2>
            <div class="box">
                <div class="wave">
                    <svg xmlns="http://www.w3.org/2000/svg" width="fit-content" height="126" viewBox="0 0 1095.3 126"><path d="M2.3 58s70 50.4 177 52c101.5 1.5 145.1-20.7 170-31.8 5.9-2.6 38.9-20.5 38.9-20.5 3.8-2.8 72.7-43.4 159.4-43.7s132.1 29.3 162.3 45.4c0 0 26.6 14.5 36.7 19.3 2.9 1.4 64.7 29.3 169.7 30.3s166-46.3 178-50" fill="none" stroke-width="2" stroke="#f1cfc6"/></svg>
                </div>
                <div class="row">
                    <ProcessComponent v-for="(item,index) in workProcess" :key="index" :obj="item"/>
                    <!-- <div class="coll">
                        <div class="img"></div>
                        <h3>First there is an idea</h3>
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit Accusantium, cumque asperiores!</p>
                    </div> -->
                </div> 
            </div>
        </div>
    </section>
</template>

<script>
import {process} from '../data/arrays';
import ProcessComponent from './ProcessComponent.vue';

    export default {
    name: "AppWorkingProcess",
    components: { ProcessComponent },
    data(){
            return {
                workProcess: process,
            }
        }
}
</script>

<style lang="scss">
@use '../assets/styles/partials/variables' as *;
@use '../assets/styles/partials/mixins' as *;

    #process{
        text-align: center;
        margin-top: 6.5rem;
        margin-bottom: 6.5rem;

       
        .box{
            width: 100%;
            // margin-top: -11rem;

            .wave{
                margin-top: 5rem;
                padding: 0 5rem;
            }

            .row{
                width: 100%;
                @include dflex-center;
                margin-top: -11rem;
            }
        }
        
    }
</style>