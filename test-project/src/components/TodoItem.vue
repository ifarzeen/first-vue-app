<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">

     

            <p>
            <!-- mark complete is a method just like an event listener -->
                <input type="checkbox" v-on:change="markComplete"/> 
                {{todo.title}}
                <button @click="$emit('del-todo',todo.id)" 
                 class="del">x</button>
            </p>
        


    </div>
</template>

<script>
export default {
    name: "TodoItem",
    // sincewehave written v-bind wala stuff in the parent of this file we need to set props here/
    props:["todo"],

    // on change method is defined here as an object of methods

    methods:{
        markComplete(){
            this.todo.completed=! this.todo.completed; 
        }
    }


}
</script>

<style scoped>
.todo-item{
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px solid purple;
}

.is-complete{
    text-decoration: line-through;
}

.del{
    background: red;
    color: #FFF;
    border:none;
    padding: 5px 10px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
}
</style>