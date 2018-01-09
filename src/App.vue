
<template>
  <div id="app">
    <todo-list v-bind:todos="todos"></todo-list>
    <create-todo v-on:create-todo="createTodo"></create-todo>
  </div>
</template>

<script>
import TodoList from './components/TodoList';
import CreateTodo from './components/CreateTodo';
export default {
  name: 'app',
  components:{
    TodoList,
    CreateTodo,
  },
  data(){
      return{
        todos:[{
          title:'todo a',
          project:'react',
          done:false,
        },
        {
          title:'todo b',
          project:'node',
          done:true,
        },
        {
          title:'todo c',
          project:'vue',
          done:false,
        },
        {
          title:'todo d',
          project:'hue',
          done:true,
        }],
    };
  },
  methods:{
    createTodo(newTodo){
      this.todos.push(newTodo);
    },
  },
};
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
</style>
