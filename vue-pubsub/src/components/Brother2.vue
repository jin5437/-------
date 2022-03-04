<template>
  <div class="outer">
    <h2>我是Brother2组件</h2>
    <h3>姓名：{{name2}}</h3>
    <button @click="sendName">点我将Brother2的姓名传给Brother1</button>
  </div>
</template>

<script>
import pubsub from 'pubsub-js'
export default {
  name:'Brother2',
  data(){
    return{
      name2:"小王"
    }
  },
  methods: {
    sendName(){
      pubsub.publish('helloName',this.name2) //发布消息
    }
  },
}
</script>

<style scoped>
.outer{
  width: 400px;
  height: 400px;
  background-color: pink;
  margin-left: 30px;
  margin-top: 50px;
  float: left;
}
</style>