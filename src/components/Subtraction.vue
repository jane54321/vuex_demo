<template>
    <div>
        <!-- <h3>当前最新的count值为：{{count}} </h3> -->
        <h3>{{showNum}}</h3>
        <button @click="btnHandler1">-1</button>
        <button @click="btnHandler2">-N</button>
        <button @click="btnHandler3">-1 Async</button>
        <button @click="subNAsync(6)">-N Async</button>
    </div>
</template>
<script>
import { mapState , mapMutations, mapActions, mapGetters } from 'vuex'
export default {
    data() {
        return {

        }
    },
    // ...   代表展开运算符  意思是把全局里面的那些数据映射为我当前组件的一个计算属性
    computed: {
        ...mapState(['count']),
        ...mapGetters(['showNum'])
    },
    methods: {
        ...mapMutations(['sub','subN']),
        ...mapActions(['subAsync','subNAsync']),
        btnHandler1() {
            this.sub()
        },
        btnHandler2() {
            this.subN(3)
        },
        btnHandler3() {
            this.subAsync()
        }
        
        
    }
}
</script>
<style lang="less" scoped>

</style>