<template>
    <div>
        <h1>記事個別ページ</h1>
        <h2>{{ post.title }}</h2>
        <p>{{ post.body }}</p>
    </div>
</template>

<script>
import axios from 'axios'

export default {
    async asyncData({ params }){
        // console.log(context)
        const { data } = await
        axios.get('https://jsonplaceholder.typicode.com/posts/' + params.id)
        return {post: data }
    },
}

</script>