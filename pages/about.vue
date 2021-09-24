<template>
    <div>
        <h1 style="text-align: center;">About Page</h1>
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
};

</script>