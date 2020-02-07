<template>
    <scroll-view class="post">
        <text class="loading" v-if="post === false">Загрузка...</text>
        <view>
            <text class="post__title">{{ post.title }}</text>
            <text class="post__date">{{ post.date }}</text>
            <text class="post__text">{{ post.body }}</text>
            <image
                v-for="image in post.images"
                class="post__image"
                :style="{width: '100%', height: 230}"
                :source="{uri: image}"
            />
        </view>
    </scroll-view>
</template>

<script>
    export default {
        props: {
            navigation: {
                type: Object
            }
        },
        async mounted() {
            await this.getPost();
        },
        data() {
            return {
                post: false
            }
        },
        methods: {
            async getPost() {
                let res = await fetch(`http://ktka.protasevich.fun/public/api/news/${this.navigation.getParam('id')}`);
                this.post = await res.json();
            }
        }
    }
</script>

<style scoped>
    .post {
        padding: 20px;
    }

    .post__title {
        font-size: 20px;
        color: #0288d1;
        margin-bottom: 10px;
    }

    .post__date {
        color: #000000;
        font-weight: bold;
        margin-bottom: 10px;
    }

    .post__text, .post__image {
        margin-bottom: 10px;
    }
</style>