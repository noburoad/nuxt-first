<template>
    <div>
        <h1>記事個別ページ</h1>
        <h2>{{ post.title }}</h2>
        <p>{{ post.body }}</p>
    </div>
</template>

<script>

export default {
    async asyncData({ params, $axios }){
        // console.log(context)
        const  post  = await $axios.$get('/posts/' + params.id)
        // console.log(post)
        return { post }
        
    },
    head(){
        return{
            title: this.post.title,
        }
    }
}
</script>