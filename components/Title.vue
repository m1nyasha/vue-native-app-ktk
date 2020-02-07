<template>
    <text class="title">
        {{ title }}
    </text>
</template>

<script>
    export default {
        props: {
            title: String
        }
    }
</script>

<style scoped>
    .title {
        text-align: center;
        margin-top: 5px;
        margin-bottom: 5px;
        font-size: 18px;
    }
</style>