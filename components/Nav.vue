<template>
    <div>
        <nav>
        <nuxt-link to="/">ホーム</nuxt-link>
        <nuxt-link to="/about"  no-prefetch>アバウト</nuxt-link>
        <nuxt-link :to="{ name: 'users-list' }">ユーザー一覧</nuxt-link>
        </nav>
    </div>
</template>