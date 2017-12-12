<template>
    <div class='ui basic content center aligned segment'>
        <button class='ui basic button icon' v-on:click="openForm" v-show="!isCreating">
            <i class='plus icon'></i>
        </button>
        <div class='ui centered card' v-show="isCreating">
            <div class='content'>
                <div class='ui form'>
                    <div class='field'>
                        <label>Title</label>
                        <input v-model="titleText" type='text' ref='title' defaultValue="">
                    </div>
                    <div class='field'>
                        <label>Project</label>
                        <input type='text' v-model="projectText" ref='project' defaultValue="">
                    </div>
                    <div class='ui two button attached buttons'>
                        <button class='ui basic blue button' v-on:click="sendForm">
                            Create
                        </button>
                        <button class='ui basic red button' v-on:click="closeForm">
                            Cancel
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

    export default {
        name:'createTodo',
        data(){
            return {
                titleText:'',
                projectText:'',
                isCreating:false,
            }
        },
        methods:{
            clean(){
                this.projectText=''
                this.titleText=''
            },
            openForm(){ this.isCreating =  true },
            closeForm(){ this.clean()
                        this.isCreating = false },
            sendForm(){
                if (this.titleText.length <= 0){
                    return;
                }
                if (this.projectText.length <= 0){
                    return;
                }
                const titleText = this.titleText;
                const projectText = this.projectText;
                this.$emit('add-todo', {titleText, projectText, done:false} )
                this.closeForm()
            },
        }
    }

</script>

<style>

</style>