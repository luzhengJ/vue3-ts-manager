
<template>
<h2 class="home">{{count}}</h2>
<button @click="handleClick">添加</button>

<el-button>Default</el-button>
    <el-button type="primary">Primary</el-button>
    <el-button type="success">Success</el-button>
    <el-button type="info">Info</el-button>
    <el-button type="warning">Warning</el-button>
    <el-button type="danger">Danger</el-button>
</template>


<script setup lang="ts">
import {ref,computed} from 'vue'
// 引入
import {useStore} from '../store'
const num = ref(0)
const store = useStore()
const count =computed(()=>{
   return store.getters.getCount
})

//添加事件
const handleClick=()=>{
  num.value+=1
   store.commit("setCount",num.value)
}
// const count = ref(0)
</script>

<style lang="scss" scoped>
.home{
  color: blue;
}
</style>
