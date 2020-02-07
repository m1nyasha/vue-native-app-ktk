<template>
    <scroll-view class="news">
        <text class="loading" v-if="news === false">Загрузка...</text>
        <view class="news__item" v-for="item in news">
            <text class="news__title">{{ item.title }}</text>
            <text class="news__body">{{ item.body }}</text>
            <text class="news__date">{{ item.date }}</text>
            <button title="Подробнее" :on-press="() => goToPostScreen(item.id)" color="#0288d1" />
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
            await this.getNews();
        },
        data() {
            return {
                news: false
            }
        },
        methods: {
            async getNews() {
                let res = await fetch(`http://ktka.protasevich.fun/public/api/news`);
                this.news = await res.json();
            },
            goToPostScreen(id) {
                this.navigation.navigate('OnePost', {id: id});
            }
        }
    }
</script>

<style scoped>
    .news {
        padding: 20px;
    }

    .news__item {
        margin-bottom: 20px;
        padding-bottom: 10px;
    }

    .news__title {
        font-weight: bold;
        font-size: 16px;
        margin-bottom: 10px;
    }

    .news__body {
        margin-bottom: 10px;
    }

    .news__date {
        text-align: right;
        color: #0288d1;
        font-weight: bold;
        margin-bottom: 10px;
    }

    .loading {
        text-align: center;
    }
</style>