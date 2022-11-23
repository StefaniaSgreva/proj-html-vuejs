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
            width: 160px;
        }
        h3{
            font-size: 1.5rem;
            font-weight: 400;
            margin-bottom: 1rem;
        }
        
        p{
            font-size: 1rem;
            width: 300px;
            margin: auto;
        }

}
  
</style>