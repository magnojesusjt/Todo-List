<template>
  <p>Add: {{ task.title }}</p>
  <form>
    <input id="task" type="text" placeholder="Add a new Task"  v-model="task.title" maxlength="50">
    <!-- feito um ternario para a exebicao do nome do button -->
    <button type="button" @click="submitTask">Save</button>
  </form>
</template>
<script setup>
import { ref, watch } from 'vue'


const emit = defineEmits(['addTask', 'editTask'])

const props = defineProps(['taskSelected'])



// Quando o id for -1, quer dizer que é uma nova tasks
const task = ref({
  title: '',
  id: -1
}) 


// Watch fica observando essa props recebida pelo o componente pai, quando selecionamos uma tasks para editar, a funcao é ativada e faz as atribuicoes necessarias
watch(props.taskSelected, () => {
  task.value.title = props.taskSelected.title
  task.value.id = props.taskSelected.id
  
})

// funcao para enviar uma task
const submitTask = () => {
    //if para verificar se é para edicao ou criacao
    if(task.value.id >= 0){
      //fazendo uma copia do objeto para o data
      let data = {...task.value}
      //enviado o data para a funcao recebida do componente pai
      emit('editTask', data)
      // resetando os valores
      task.value.title = ''
      task.value.id = -1
     
      return
    }

    //enviado uma nova task

    emit('addTask', task.value.title)

    task.value.title = ''
} 

</script>
<style scoped>
  p{
    text-align: center;
    font-weight: 700;
    background-color: rgb(131, 35, 35);
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
  