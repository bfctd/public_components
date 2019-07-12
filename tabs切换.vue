<template>
    <div class="m-bz-nav-router">
        <router-link tag="div" class="bz-item-box" to="/about">
            <div class="bz-item">
                <div class="bz-img-icon"></div>
                <div class="bz-font-icon"></div>
                <p>首页</p>
            </div>
        </router-link>
        <router-link tag="div" class="bz-item-box" to="/about">
            <div class="bz-item">
                <div class="bz-img-icon"></div>
                <div class="bz-font-icon"></div>
                <p>tab2</p>
            </div>
        </router-link>
        <router-link tag="div" class="bz-item-box" to="/about">
            <div class="bz-item">
                <div class="bz-img-icon"></div>
                <div class="bz-font-icon"></div>
                <p>tab3</p>
            </div>
        </router-link>
        <router-link tag="div" class="bz-item-box" to="/about">
            <div class="bz-item">
                <div class="bz-img-icon"></div>
                <div class="bz-font-icon"></div>
                <p>我的</p>
            </div>
        </router-link>
    </div>
</template>

<script>
    export default {
        name: 'MBzNavRouter'
    }
</script>

<style scoped lang="scss">
    /*@import "../../../lib.scss";*/

    .m-bz-tabs {
        width: 100%;
        height: 55px;
        border-top: 1px solid #efefef;

        .bz-item-box {
            display: flex;
            justify-content: center;
            align-items: center;
            float: left;
            //修改
            width: 25%;
            text-align: center;
            font-size: 14px;
            height: 100%;
            border-right: 0 solid #efefef;

            .bz-item {
                .bz-img-icon {
                    //修改
                    @include bgImage(20px, "../assets/logo.png");
                    background-size: 100% auto;
                    margin: 0 auto;
                }

                & .bz-img-icon:nth-child(2) {
                    @include bgImage(20px, "../assets/logo.png");
                    background-size: 100% auto;
                }

                & .bz-img-icon:nth-child(3) {
                    @include bgImage(20px, "../assets/logo.png");
                    background-size: 100% auto;
                }

                & .bz-img-icon:nth-child(4) {
                    @include bgImage(20px, "../assets/logo.png");
                    background-size: 100% auto;
                }

                &:after {
                    display: block;
                    content: ".";
                    clear: both;
                    font-size: 0;
                    line-height: 0;
                    height: 0;
                    visibility: hidden;
                }
            }

            &:last-child {
                border-right: 0;
            }
        }
    }
</style>
