<template>
    <view class="header" :style="{backgroundColor: color}">
        <touchable-opacity class="burger" :on-press="goToMenuScreen">
            <view class="burger__item"></view>
            <view class="burger__item second"></view>
            <view class="burger__item third"></view>
        </touchable-opacity>
        <text class="header__text">
            {{ title }}
        </text>
    </view>
</template>

<script>
    export default {
        props: {
            title: String,
            color: String,
            navigation: {
                type: Object
            }
        },
        methods: {
            goToMenuScreen() {
                this.navigation.openDrawer();
            }
        }
    }
</script>

<style scoped>

    .header {
        position: relative;
        padding-top: 10px;
        padding-bottom: 10px;
        /*margin-bottom: 20px;*/
    }

    .header__text {
        font-size: 24px;
        text-transform: uppercase;
        text-align: center;
        color: #fff;
    }

    .burger {
        position: absolute;
        width: 30px;
        height: 30px;
        top: 50%;
        left: 10px;
        z-index: 999;
    }

    .burger__item {
        position: absolute;
        width: 100%;
        height: 3px;
        background-color: #fff;
        border-radius: 5px;
    }

    .second {
        top: 8px;
    }

    .third {
        top: 16px;
    }

</style>