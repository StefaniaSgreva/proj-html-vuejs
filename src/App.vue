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
  <!-- FIXED ELEMENTS -->
  <div class="arrow-up" ref="arrow">
    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="23"><path fill="#FFF" stroke="#FFF" stroke-width="2" stroke-linecap="round" stroke-miterlimit="10" d="M10 21.5v-19"/><path fill="#FFF" d="M3.926 7.484c-.388-.404-.388-.801 0-1.188L9.419.803c.14-.176.334-.264.58-.264s.44.088.582.264l5.493 5.493c.387.388.387.784 0 1.188-.389.405-.775.396-1.162-.026L9.999 2.599 5.088 7.458c-.388.422-.775.432-1.162.026z"/></svg>
  </div>
  <div class="aside-menu">
    <div class="related">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 87 87" style="height:26px" fill="#fff"><path d="M55.4 81.5c6.1-11.1 5.2-16.1-4.3-24.3 6.1-3.5 9.5-8.5 9.1-15.7-.5-8.2-7.7-14.7-16.3-14.6-8.5.1-15.6 6.7-15.9 15-.3 8.5 5.9 15.8 14.3 16.6 1.4.1 2.8.2 4.2.5 5.9 1.2 10.2 6.7 9.8 12.6-.4 6.4-5.5 11.4-11.8 11.7-19.6.9-38.6-14.8-41.3-34C-.1 26.9 14.4 6.8 36.4 2.8c22.3-4 43.4 10 48.1 32 4.3 20-8.6 41.2-28.4 46.7h-.7z"/></svg>
    </div>
    <div class="shop">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" style="height:16px" fill="#ee2852"><circle cx="9" cy="21" r="2"/><circle cx="20" cy="21" r="2"/><path d="M23.8 5.4c-.2-.3-.5-.4-.8-.4H6.8L6 .8C5.9.3 5.5 0 5 0H1C.4 0 0 .4 0 1s.4 1 1 1h3.2L5 6.2v.1l1.7 8.3C7 16 8.2 17 9.6 17H19.4c1.5 0 2.7-1 3-2.4L24 6.2c0-.3 0-.6-.2-.8z"/></svg>
    </div>
  </div>
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
    AppBlog,
    AppFooter
},
    data(){
      return{

      }
    },
    methods: {
      vueOnScroll() {
        let prev = window.pageYOffset;
        const refs = this.$refs.arrow; 
        window.addEventListener("scroll", () => {
          let curr = window.pageYOffset;
          if (prev > curr) {
            refs.classList.add("scrollDown");
            refs.classList.remove("scrolled");
          } else {
            refs.classList.add("scrollDown");
            refs.classList.remove("scrolled");
          }
          if (curr === 0) {
            refs.classList.remove("scrollDown");
            refs.classList.remove("scrolled");
          }
            prev = curr;
        });
      }
    },
    mounted() {
      this.vueOnScroll();
    }

}
</script>

<style lang="scss" scoped>
@use './assets/styles/partials/variables' as *;
@use './assets/styles/partials/mixins' as *;

.arrow-up{
    padding: .65rem 1rem;
    background-color: $bg-color-mint;
    position: fixed;
    bottom: 2rem;
    right: 1.5rem;
    z-index: 10;
    opacity: 0;
    transition: opacity 450ms ease;
  }

  .scrolled{
    opacity: 0;

    }
    .scrollDown{
      opacity: 1;
    }
  .aside-menu{
    position: fixed;
    top: 12rem;
    right: 0;
    z-index: 10;
    display: flex;
    flex-direction: column;
    row-gap: .50rem;

    .related{
      background-color: $aside-menu;
      padding: .55rem;
      text-align: center;
      @include dflex-center;
    }
    .shop{
      background-color: $bg-color-white;
      box-shadow: 0 0 8px 0 $shadow;
      text-align: center;
      padding: .75rem .55rem;
      @include dflex-center;
    }
  }
</style>