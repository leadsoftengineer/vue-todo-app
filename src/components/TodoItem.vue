<!--KYIV MEDIA 3.12.2019 -->
<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <p>
            <input type="checkbox" v-on:change="markComplete">
            {{todo.title}}
            <button @click="$emit('del-todo',todo.id)" class="del">X</button>
        </p>
    </div>
</template>

<script>
import { log } from 'util'
export default {
    name:"TodoItem",
    props:["todo"],
    methods:{
        markComplete(){
            this.todo.completed = !this.todo.completed;
            
        }
    }
}
</script>

<style scoped>
.todo-item{
    background-color: lightgrey;
    padding:10px;
    border-bottom:1px dotted;
}
.is-complete{
    text-decoration: line-through;
}
.del{
    background:red;
    color:white;
    border:none;
    padding: 5px 9px;  
    border-radius: 50%;
    cursor:pointer;
    float:right;
}
</style>