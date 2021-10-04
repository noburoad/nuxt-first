<template>
    <div>
        <h1>記事一覧</h1>
        <ul>
            <li v-for="post in posts" :key=post.id>
                <nuxt-link :to=" '/posts/' + post.id ">{{ post.title }}</nuxt-link>
            </li>
        </ul>
    </div>
</template>
<script>
import axios from 'axios'
export default {
    async asyncData(context){
        //asyncとawaitを使用してサーバーで処理してからクライアントへ返すようにしている
        //nuxt.config.jsのbaseURLにjsonplaceholderのURLを記述してるのでパスを/posts/にできる
        const posts = await context.$axios.$get('/posts/')

        const users = await context.$axios.$get('/users/')
        return { posts, users }
    },
    // data(){
    //     return{
    //         posts: []
    //     }
    // },
    // mounted(){
    //     axios.get('https://jsonplaceholder.typicode.com/posts')
    //         .then(respons => this.posts = respons.data)
    // }
}
</script>