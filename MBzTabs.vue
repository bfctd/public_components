<template>
    <div class="m-bz-tabs">
        <div class="bz-tabs-box">
            <div class="bz-tabs-option" :class="{'active':contentIndex===i}" v-for="(v,i) in tabs" @click="clickTab(i)">
                <p>{{v.name}}</p>
            </div>
        </div>
        <div ref="tabsContent" class="bz-tabs-content">
            <slot></slot>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'MBzTabs',
        props: {
            tabs: {
                type: Array,
                default: () => [],
                required: false
            },
            tabName: {
                default: 'name'
            }
        },
        data() {
            return {
                contentIndex: 0,
                _contentIndex: 0,
                tabsContent: [] //tabs的内容的dom List
            }
        },
        mounted() {
            console.log(this.$refs.tabsContent)
            this.tabsContent = this.$refs.tabsContent.querySelectorAll(".m-bz-tabs-content-item")
            this.tabsContent[this.contentIndex].style.display = "block"
        },
        methods: {
            clickTab(index) {
                this._contentIndex = this.contentIndex
                this.contentIndex = index
                if (!(this.contentIndex === this._contentIndex)) {
                    this.tabsContent[this.contentIndex].style.display = "block"
                    this.tabsContent[this.contentIndex].className = "active"
                    this.tabsContent[this._contentIndex].style.display = "none"

                }
            }
        }
    }
</script>

<style scoped lang="scss">
    @import "lib";

    .m-bz-tabs {

        .bz-tabs-box {
            width: 100%;
            height: 45px;
            display: flex;
            align-items: center;
            overflow-x: auto;

            .bz-tabs-option {
                height: 100%;
                flex-grow: 1;
                min-width: 22%;
                display: flex;
                align-items: center;
                justify-content: center;
                border-bottom: 1px solid #efefef;

                &.active {
                    border-bottom-color: red;
                    color: red;
                }
            }
        }

        .bz-tabs-content {
            width: 100%;
            overflow-x: hidden;
        }
    }
</style>
