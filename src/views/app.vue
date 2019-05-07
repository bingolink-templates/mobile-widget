<template>
    <div class="center">
        <bui-image src="/image/logo.png" width="120px" height="120px"></bui-image>
        <text class="h2" style="color:red;">移动端小部件模板</text>
        <text class="h4">BUI-Weex版</text>
    </div>
</template>

<!--引入bui-weex样式文件-->
<style lang="scss" src="bui-weex/src/css/buiweex.scss"></style>

<script>
    var globalEvent = weex.requireModule('globalEvent');
    module.exports = {
        data () {
            return {}
        },
        mounted()
        {
        }
    }
</script>