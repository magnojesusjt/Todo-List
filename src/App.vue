<script setup>
import { ref } from 'vue'
import TodoHeader from './components/TodoHeader.vue'
//import TodoTaskDisplay from './components/TodoTaskDisplay.vue'
import TodoTaskInput from './components/TodoTaskInput.vue'
import TodoTaskHeader from './components/TodoTaskHeader.vue'
import TodoTaskTable from './components/TodoTaskTable.vue'

// Variavel usada para armazenar todas as tasks
const tasks = ref([])


//Variavel usada quando for selecionada alguma task para edicao
const taskSelected = ref({
    title: '',
    id: ''
})


// funcao para inserir uma nova task
const addTask = (value) => {
    tasks.value.push({title: value})
}


// funcao para editar uma task, o value.id é a posicao do array
const editTask = (value) => {
   tasks.value[value.id].title = value.title
}

// funcao para remover um array pela posicao
const deleteTask = (id) => {
    tasks.value.splice(id, 1)
    //corrigindo um bug. ao clicar em editar e depois em excluir, o campo ainda fica preenchido
    taskSelected.value.title = ''
    taskSelected.value.id = -1
}

// funcao para renderizar uma task selecionada para edicao
const renderTask = (id) => {
    taskSelected.value.title = tasks.value[id].title
    taskSelected.value.id = id
  
}




</script>
<template>
    <main>
    <TodoHeader />
    <!--<TodoTaskDisplay />-->
    <!-- Esse componente recebe duas funções e uma variavel -->
    <TodoTaskInput @editTask="editTask" @addTask="addTask" :taskSelected="taskSelected"/>
    <!-- <TodoTaskHeader /> -->
    <!-- Esse componente recebe duas funções e uma variavel -->
    <TodoTaskTable :tasks="tasks" @renderTask="renderTask" @deleteTask="deleteTask" />
    </main>
</template>



<style scoped>
main{
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 13px;
}
</style>
