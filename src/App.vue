<script setup>
import TodoHeader from './components/TodoHeader.vue'
//import TodoTaskDisplay from './components/TodoTaskDisplay.vue'
import TodoTaskInput from './components/TodoTaskInput.vue'
import TodoTaskHeader from './components/TodoTaskHeader.vue'
import TodoTaskTable from './components/TodoTaskTable.vue'

</script>
<template>
    <main>
    <TodoHeader />
    <!--<TodoTaskDisplay />-->
    <TodoTaskInput />
    <TodoTaskHeader />
    <TodoTaskTable />
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
