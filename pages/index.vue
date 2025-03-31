<template>
    <h1>Hello Babe</h1>
   <p>From the api/hello: {{ data.hello }}</p> 
</template>
<script setup>
const { data } = useFetch('/api/hello')
</script>