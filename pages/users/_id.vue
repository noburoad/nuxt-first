<template>
    <h1 style="text-arign: center;">ユーザー：ID {{ user.name }}</h1>
</template>

<script>
export default {
    head(){
        return{
            title: this.user.name ,
        }
    },
    //ユーザーデータを仮で作成（本当はaxiosなどでAPIを使いバックエンドから取得）
    data() {
        return{
            //this.$route.params.idでURLのidなどを取得できる
            id: this.$route.params.id,
            users: [
                {
                    id: 1,
                    name: 'Nobu'
                },
                {
                    id: 2,
                    name: 'Rie'
                },
                {
                    id: 3,
                    name: 'Aoi'
                },
                {
                    id: 4,
                    name: 'Yuuri'
                },
            ],
        }
    },
    //computedプロパティでブラウザで入力されたIDとデータプロパティのusersのidをチェック
    computed:{
        user(){
            return this.users.find(user => user.id ==this.id)
        }
    },
    //nuxt.jsはmountedはクライアント側だけで実行され、createdはサーバ側とクライアント側で実行される
    mounted() {
        console.log(this.$route);
    },
    created() {
        console.log(this.$route);
    }
}
</script>