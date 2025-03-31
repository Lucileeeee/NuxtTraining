<template>
     <h1>Page Article de Blog</h1>
     <div v-if="post">
        <h2> {{ post.title }} </h2>
        <p> {{ post.body }} </p>
     </div>
     <div v-else="!post">
            <p>Chargement ... </p>
     </div>
  
</template>

<script setup lang="ts">

const route = useRoute()
const {data:post} = useFetch(()=> "https://jsonplaceholder.typicode.com/posts/" + route.params.id ,
{ lazy:true} )
useSeoMeta({
    title: ()=>post.value?.title
})
</script>