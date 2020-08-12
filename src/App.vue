<template>
  <div id="app" class="container">
    <h3>Bunch of todos from JSON placeholder</h3>
      <div class="input-area">
        <input type="text" v-model="limit" class="text" placeholder="Enter the Count of todo's" />
        <input v-on:click="limitchange" type="button" class="btn blue" value="GO!"/> 
      </div>
    <Todos v-bind:todos="todos"/>
  </div>
</template>

<script>
import axios from 'axios'
import Todos from './components/Todos'

export default {
  name:"App",
  components:{
    Todos
  },
  data(){
    return{
        limit : '',
        todos : []
    }
  },
  methods:{
    limitchange(){
       axios.get(`https://jsonplaceholder.typicode.com/todos/?_limit=${this.limit}`)
        .then((res)=> this.todos = res.data)
    }
  }
}
</script>

<style>
#app{
  font-family: 'Poppins';
}
#app h3{
  text-align:center;
  font-weight: 400;
}
.input-area{
  display: flex;
  justify-content: center;
  align-items: center;
}
.text{
  max-width: 200px;
}
.btn{
  margin-left: 20px;
}

</style>
