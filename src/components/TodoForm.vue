<script setup>
import { ref } from 'vue'
import { useTodoListStore } from '@/stores/todoList'
import func from '../../vue-temp/vue-editor-bridge'

const todo = ref('')

const store = useTodoListStore()

function addItemAndClear(item){
    if(item.length === 0){
        return;
    }
    store.addTodo(item)
    todo.value = ''
}

</script>
<template>
    <div>
        <form @submit.prevent="addItemAndClear">
            <input v-model="todo" type="text">
            <button>Add</button>
        </form>
    </div>
</template>



<style>

</style>