<template>
    <div id="app">
        <el-main>
            <Navigation></Navigation>
            <router-view></router-view>
        </el-main>
        <UpdateRestaurantModal></UpdateRestaurantModal>
        <RestaurantModal></RestaurantModal>
    </div>
</template>

<script>
import Navigation from './containers/Navigation'
import UpdateRestaurantModal from './containers/Restaurants/UpdateRestaurantModal';
import RestaurantModal from './containers/Restaurants/RestaurantModal';

export default {
    name: 'app',
    components: {
        Navigation,
        UpdateRestaurantModal,
        RestaurantModal,
    }
}
</script>

<style>
#app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
}
</style>
