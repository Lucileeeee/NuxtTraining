<template>
        <h1>Page Blog</h1>
    <article v-if="posts" v-for="post in posts" :key="post.id">
       <h1>id: {{ post.id }}</h1> 
       <h1>titre: {{ post.title }}</h1>
       <NuxtLink :to ="`/blog/${post.id}`">Lire l'Article</NuxtLink>   
    </article>
    <div v-else="!posts">
       <p>Chargement en cour ...</p> 
    </div>


</template>

<script setup lang="ts">


const { data:posts } = await useFetch('https://jsonplaceholder.typicode.com/posts/');


</script>