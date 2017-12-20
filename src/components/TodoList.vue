<template>
    <div>
        <div>
            // JavaScript expressions in Vue are enclosed in double curly brackets.
            <p>Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</p>
            <p>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
        </div>
        <div class="flexcontainer">
            <todo v-bind:todo.sync="todoItem"
                  v-for="todoItem in todos"
                  v-bind:key="todoItem.done"
                  v-on:delete-todo="deleteTodo"
                  v-on:complete-todo="completeTodo" />
        </div>
        <div><p>&nbsp;</p></div>
    </div>
</template>


<script>

    import sweetalert from 'sweetalert';
    import Todo from './Todo'

    export default {
        props: ['todos'],
        components: {
            Todo,
        },
        methods:{
            deleteTodo(todoItem) {
                sweetalert({
                        title: 'Are you sure?',
                        text: 'This To-Do will be permanently deleted!',
                        icon: "warning",
                        buttons: true,
                        dangerMode: true,
                    }).then((willDelete) => {
                    if (willDelete) {
                        const todoIndex = this.todos.indexOf(todoItem);
                        this.todos.splice(todoIndex, 1);
                        sweetalert("To-Do has been deleted", { icon: "success", });
                    }
                });
            },
            completeTodo(todoItem){
                const todoIndex = this.todos.indexOf(todoItem)
                this.todos[todoIndex].done = true
                sweetalert("To-Do completed!", { icon: "success", });


            }
        }
    }

</script>

<style>
.flexcontainer{
    display:flex;
    flex-direction: row;
    flex-wrap: nowrap;
    align-self: flex-start;
    width:1200px;
}
</style>