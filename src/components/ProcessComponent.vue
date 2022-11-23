<template>
    <div class="col">
        <img :src="obj.img" alt="">
        <h3>{{obj.title}}</h3>
        <p>{{obj.text}}</p>
    </div>
</template>

<script>
    export default {
        name: 'ProcessComponent',
        props:[

            'obj'
        ]
    }
</script>

<style lang="scss" scoped>
.col{
    flex-basis: calc(100% / 4);
    padding: 2rem .25rem;

        img{
            margin: 1.5rem auto;
        }
        
        p{
            font-size: .85rem;
        }

}
  
</style>