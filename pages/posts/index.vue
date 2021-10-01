<template>
    <div>
        <h1>記事一覧</h1>
        <ul>
            <li v-for="post in posts" :key=post.id>
                {{ post.title }}
            </li>
        </ul>
    </div>
</template>
<script>
import axios from 'axios'
export default {
    async asyncData(){
        //asyncとawaitを使用してサーバーで処理してからクライアントへ返すようにしている
        const responsePost = await
            axios.get('https://jsonplaceholder.typicode.com/posts/')
        const responseUser = await
            axios.get('https://jsonplaceholder.typicode.com/users/')
        return { posts: responsePost.data, users: responseUser.data }
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