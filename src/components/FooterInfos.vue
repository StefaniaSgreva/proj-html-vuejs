<template>
   <ul>
        <li v-for="(info,index) in item.infos" :key="index">{{info.text}}</li>
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
ul{
    margin-right: 8rem;
    line-height: 1.8rem;
}
</style>