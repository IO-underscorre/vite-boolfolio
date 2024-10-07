<script>
import TopBar from './TopBar.vue';

export default {
    name: 'AppHeader',

    components: {
        TopBar,
    }
}
</script>

<template>
    <header>
        <TopBar />
    </header>
</template>

<style lang="scss" scoped>
header {
    padding-top: $hgt-topbar;
}
</style>