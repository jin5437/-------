<template>
  <div class="outer">
    <h2>我是Brother1组件</h2>
    <h3>姓名：{{name1}}</h3>
  </div>
</template>

<script>
import pubsub from 'pubsub-js'
export default {
  name:'Brother1',
  data(){
    return{
      name1:"小李"
    }
  },
  // methods: {
  //   demo(msgName,data){
  //     console.log('消息名字是:',msgName);
  //     console.log('我是Brother1组件，我收到了Brother2组件的name：',data);
  //   }
  // },
  mounted() {  
    // 订阅消息
    this.pid = pubsub.subscribe('helloName',(msgName,data) => {
      console.log('消息名字是:',msgName);
      console.log('我是Brother1组件，我收到了Brother2组件的name：',data);
    })
    
  },
  beforeDestroy(){
    pubsub.unsubscribe(this.pid)
  }
}
</script>

<style scoped>
.outer{
  width: 400px;
  height: 400px;
  background-color: lightblue;
  margin-left: 30px;
  margin-top: 50px;
  float: left;
}
</style>