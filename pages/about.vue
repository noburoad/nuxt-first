<template>
    <div>
        <h1 style="text-align: center;">アバウト</h1>
        <h2>{{ subtitle }}</h2>
    </div>
</template>

<script>
export default {
    layout: "original",
    data(){
            return {
                subtitle: 'サブタイトルです'
            }
        },
    head(){
        return {
            title: 'アバウトページだよん',
            meta: [
                {
                    hid: 'discription', name: 'discription', content: 'アバウトページです'
                }
            ]
        }
    }
};

</script>
