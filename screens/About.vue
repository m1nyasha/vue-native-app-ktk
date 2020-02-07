<template>
    <view class="about">
        <image
            :style="{width: 200, height: 200}"
            :source="{uri: 'https://sun9-48.userapi.com/c855132/v855132370/71121/C3UJujY0gMU.jpg'}"
        />
        <text class="about__text">
            Разработчик: Михаил Протасевич
        </text>
    </view>
</template>

<style scoped>
    .about {
        height: 100%;
        background-color: #0288d1;
        align-items: center;
        justify-content: center;
    }
    
    .about__text {
        color: #fff;
        margin-top: 10px;
    }
</style>