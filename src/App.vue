<template>
  <AppHeader/>
  <main>
    <AppHero/>
    <AppPortfolio/>
    <AppWorkingProcess/>
    <CallToAction/>
    <AppBlog/>
  </main>
  <AppFooter/>
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import AppHero from './components/AppHero.vue';
import AppPortfolio from './components/AppPortfolio.vue';
import AppWorkingProcess from './components/AppWorkingProcess.vue';
import CallToAction from './components/CallToAction.vue';
import AppBlog from './components/AppBlog.vue';
import AppFooter from './components/AppFooter.vue';


  export default {
    components: {
    AppHeader,
    AppHero,
    AppPortfolio,
    AppWorkingProcess,
    CallToAction,
    AppBlog ,
    AppFooter
},
    data(){
      return{

      }
    }
}
</script>

<style lang="scss" scoped>

</style>