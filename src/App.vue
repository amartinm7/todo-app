<template>
  <div id="app">
    <img src="./assets/logo.png">
    <todo-list v-bind:todos="todoList"/>
    <create-todo v-on:add-todo="addTodo"/>
    <div><p>&nbsp;</p></div>
  </div>
</template>

<script>

    import sweetalert from 'sweetalert';
  import TodoList from './components/TodoList'
  import CreateTodo from './components/CreateTodo'

  export default {
    name: 'app',
    components: {
      TodoList, CreateTodo,
    },
    data(){
        return {
            todoList:[{
                title: 'Todo A',
                project: 'Project A',
                done: false
            },{
                title: 'Todo B',
                project: 'Project B',
                done: true
            },{
                title: 'Todo C',
                project: 'Project C',
                done: false
            },{
                title: 'Todo D',
                project: 'Project D',
                done: false
            }
            ]
        }
    },
    methods:{
      addTodo(newTodo){
          this.todoList.push( {'title':newTodo.titleText, 'project':newTodo.projectText, done : false } )
          sweetalert("To-Do created!", { icon: "success", });
      },
    },
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
</style>
