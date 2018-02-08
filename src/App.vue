<template>
  <div id="app">
    <img src="./assets/logo.png">
    <HelloWorld/>
    <!--<TODOList :list="list"/>-->
    <!--<List/>-->
  </div>
</template>

<script>
  import HelloWorld from './components/HelloWorld'
  import TODOList from './components/TODOList'
//  import List from './components/List'

export default {
  name: 'App',
  data () {
      return {
          list:[
            {name:'张三',age:20},
            {name:'李四',age:22},
            {name:'王五',age:29}
          ],
      }
  },
  components: {
    HelloWorld,
    TODOList
//    List
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  min-height: 1600px;
}
</style>
