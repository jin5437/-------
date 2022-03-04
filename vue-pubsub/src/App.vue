<template>
  <div id="app">
    <div>
      我是父组件
    </div>
    
    <Brother1></Brother1>
    <Brother2></Brother2>
  </div>
</template>

<script>
import Brother1 from './components/Brother1'
import Brother2 from './components/Brother2'
export default {
  name: 'App',
  components: {
    Brother1,
    Brother2
  }
}
</script>

<style>
#app{

  width: 900px;
  height: 600px;
  background-color: #bfa;
  margin: 50px;
}
</style>
