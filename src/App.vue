<script>
import AppHeader from './components/layouts/AppHeader.vue';

export default {
    components: {
        AppHeader,
    }
};
</script>

<template>
    <AppHeader />
    <router-view />
</template>

<style lang="scss" scoped></style>
