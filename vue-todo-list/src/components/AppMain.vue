<script setup>
import TodoItem from './TodoItem.vue';

const tasks = [
        {id: 1, title: "Tache n°1", completed: false}, //Tache 1
        {id: 2, title: "Tache n°2", completed: false}, //Tache 2
        {id: 3, title: "Tache n°3", completed: false}, //Tache 3
    ]
</script>

<template>
    <div>
        <main class="main">
            <ul class="todolist">
                <TodoItem v-for="task in tasks" :key="task.id" :to_do="task"></TodoItem>
            </ul>
        </main>
    </div>
</template>

<style scoped>
    .todolist{
        margin: 0;
        padding: 0;
        list-style: none;
    }
    .todolist li{
        font-size: 20px;
        border-bottom: 1px solid rgb(192, 187, 187);
        position: relative;
    }
    .todolist li:last-child{
        border-bottom: none;
    }
    
</style>
