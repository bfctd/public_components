<template>
    <div class="m-bz-tabs-content-item">
        <slot></slot>
    </div>
</template>

<script>
    export default {
        name: 'MBzTabsContentItem',
    }
</script>

<style scoped lang="scss">
    @import "lib";

    .m-bz-tabs-content-item {
        display: none;
    }
</style>
