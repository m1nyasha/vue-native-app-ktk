<template>
    <view>
        <Header title="KTK" color="#0288d1" :navigation="navigation" />
        <Title title="Последние новости" />
        <NewsList :navigation="navigation" />
    </view>
</template>

<script>

    import Header from "../components/Header";
    import Title from "../components/Title";
    import NewsList from "../components/NewsList";

    export default {
        components: {
            Header,
            Title,
            NewsList
        },
        props: {
            navigation: {
                type: Object
            }
        },
        methods: {
        }
    }

</script>