<template>
    <AppNavigator />
</template>

<script>

    import {
        createAppContainer,
        createStackNavigator,
        createDrawerNavigator
    } from "vue-native-router";

    import HomeScreen from './screens/Home'
    import AboutScreen from './screens/About'
    import OnePostScreen from "./screens/OnePost";

    const DrawerNavigator = createDrawerNavigator(
        {
            Home: {
                screen: HomeScreen,
                navigationOptions: {
                    title: 'Новости',
                }
            },
            About: {
                screen: AboutScreen,
                navigationOptions: {
                    title: 'О приложении',
                }
            }
        },
        {
            initialRouteName: 'Home'
        }
    );

    const StackNavigator = createStackNavigator(
        {
            Drawer: DrawerNavigator,
            Home: HomeScreen,
            About: AboutScreen,
            OnePost: OnePostScreen,
        }
    );

    const AppNavigator = createAppContainer(StackNavigator);

    export default {
        components: {
            AppNavigator
        },
        data() {
            return {
                postId: false
            }
        }
    }

</script>
