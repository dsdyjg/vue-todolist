<template>
  <div id="app">
   <HelloWorld></HelloWorld>
   </div>
</template>

<script>
import HelloWorld from './components/HelloWorld';
export default {
  name: 'app',
  data(){
     return {
	 }
  },
  components:{HelloWorld}
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
}
ul{
   width:400px;
   margin:30px auto;
   border:1px solid #ddd;
   min-height:60px;
}
li{
   border-bottom:1px dotted #dfdfdf;
}
li .del{color:red;margin-left:20px;cursor:pointer;}
li.check{
  text-decoration:line-through;
}
</style>
