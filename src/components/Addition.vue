<template>
    <div>
        <!-- 标准的是this.$store.state.count   但是template的this可以省略-->
        <!-- <h3>当前最新的count值为：{{$store.state.count}} </h3> -->
        <h3>{{ $store.getters.showNum}}</h3>
        <button @click="btnHandler1">+1</button>
        <button @click="btnHandler2">+N</button>
        <button @click="btnHandler3">+1 Async</button>
        <button @click="btnHandler4">+N Async</button>
    </div>
</template>
<script>
export default {
    data() {
        return {

        }
    },
    methods: {
        btnHandler1() {
            this.$store.commit('add')
        },
        btnHandler2() {
            // commit 的作用， 就是调用某个mutation函数
            this.$store.commit('addN', 3)
        },
        // 异步 让count 自增 +1
        btnHandler3() {
            // 这里的 dispatch  函数，专门用来触发 action
            this.$store.dispatch('addAsync',5)
        },
         btnHandler4() {
            // 这里的 dispatch  函数，专门用来触发 action
            this.$store.dispatch('addNAsync',5)
        }
    }
}
</script>
<style lang="less" scoped>

</style>