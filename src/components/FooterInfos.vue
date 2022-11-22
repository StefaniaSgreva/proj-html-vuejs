<template>
   <ul>
        <li v-for="(info,index) in item.infos" :key="index"><span>{{info.text}}</span></li>
   </ul>
</template>

<script>
    export default {
        name: 'FooterInfos',
        props: [
            'item'
        ]
    }
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables' as *;
@use '../assets/styles/partials/mixins' as *;
ul{
    margin-right: 8rem;
    line-height: 1.8rem;
   
    li{
        cursor: pointer;
        max-width: 100%;
        font-size: .95rem;
        span{
               
               width: 100%;
               background-image: linear-gradient(to bottom,
                rgba(243,208,199,0) 60%,
                rgba(243,208,199,1) 40%,
                );
                background-size: 0 100%;
                background-repeat: no-repeat;
                transition: 450ms linear;
           }
           span:hover{
               background-size: 100% 100%;
           }
    }

}
</style>