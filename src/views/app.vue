<template>
    <div class="center" ref="wrap" style="height:100%;">
        <bui-image src="/image/logo.png" width="120px" height="120px"></bui-image>
        <text class="h2" style="color:red;">移动端小部件模板</text>
        <text class="h4">BUI-Weex版</text>
    </div>
</template>

<!--引入bui-weex样式文件-->
<style lang="scss" src="bui-weex/src/css/buiweex.scss"></style>

<script>
    var globalEvent = weex.requireModule('globalEvent');
    var dom = weex.requireModule('dom');

    module.exports = {
        data () {
            return {}
        },
        mounted()
        {
            this.broadcastWidgetHeight()
        },
        methods: {
            broadcastWidgetHeight(){
                var _params = this.$getPageParams();
                setTimeout(() => {
                    dom.getComponentRect(this.$refs.wrap , (ret) => {
                        var channel = new BroadcastChannel('WidgetsMessage')
                        channel.postMessage({widgetHeight: ret.size.height, id: _params.id});
                        channel.close();
                    });
                }, 100)
            }
        }
    }
</script>