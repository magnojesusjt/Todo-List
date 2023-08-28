<template>
  <p>Add: {{ task }}</p>
  <form @submit.prevent="addTask">
    <input id="task" type="text" placeholder="Add a new Task" v-model="task" maxlength="50">
    <button type="submit">Add</button>
  </form>
</template>
<script setup name="test">
import { ref } from 'vue'
const task = ref(" ") 
</script>
<style scoped>
  p{
    text-align: center;
    font-weight: 700;
    background-color: rgb(230, 230, 230);
    width: 700px;
    padding: 0.5px;
    border-radius: 5px;
  }
form{
  display: flex;
  flex-direction: row;
  align-items: baseline;
  gap: 10px;
  flex-wrap: wrap;
}
input{
  width: 600px;
  padding: 20px;
  border-radius: 5px;
  border: 1px solid rgba(161, 161, 161, 0.445);
  box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
}
button{
  background-color: #4099ff;
  border: 0px;
  color: white;
  font-weight: 700;
  border-radius: 5px;
  width: 70px;
  height: 40px;
}
button:hover{
  background-color: #2674ce;
  box-shadow: rgba(0, 0, 0, 0.3) 0px 3px 15px, rgba(0, 0, 0, 0.22) 0px 3px 6px;
  cursor: pointer;
}
</style>
  