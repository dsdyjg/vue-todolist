<template>
  <div id="vue-todolist" class="todolistDiv">
    <span> todolist</span>
        <input class="ipt" type="text" v-model="inputVal" v-on:keyup.enter="addItem"/>
        <ul >
            <li v-for="(item,index) in items" :key="index">
            <div class="liDiv">
                <input type="checkbox" v-model="item.isChecked" >
                <label  v-bind:class="{ complete:item.isChecked }">{{item.text}}</label>
                <span @click="delItem(index)" class="btn">X</span>
            </div>
           </li>
        </ul>
		<p>已选中{{activecounts}}/共{{items.length}}</p>
		<span>{{spanTest}}</span>
    </div>
</template>
<script>
export default {
  name: 'HelloWorld',
  props:['spanTest'],
  data () {
     return {
	   items:[],
       inputVal:""
	 }
  },
  computed:{
     activecounts(){
	    var total = 0; 
		this.items.forEach(function(item){ 
		if(item.isChecked){
		   total++;
		} 
		}); 
		return total;
	 }
  },
  methods:{
      addItem(){
        this.items.push({text:this.inputVal});
		console.log(this.items);
        this.inputVal="";
    },
    delItem(index) {
      this.items.splice(index, 1);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
.complete{color:red;}
</style>
