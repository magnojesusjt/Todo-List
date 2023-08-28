<template>
    <main>
        <section id="task-item" >
            <table width="100%">
                <!-- foi usado um v-for para percorrer o array e exebir os dados das tarefas-->
                    <tr  v-for="(item, idx) in tasks">
                        <td padding="0px" align="center" class="texto">{{item.title}}</td>
                        <td padding="0px" width="200px" align="center" display="flex">
                            <!-- Usando o emit para chamar a funcao recebida pelo componente pai e enviamos a posicao do array -->
                            <button id="edit" @click="emit('renderTask', idx)">Edit</button>
                            <!-- Usando o emit para chamar a funcao recebida pelo componente pai e enviamos a posicao do array -->
                            <button id="delete" @click="emit('deleteTask', idx)">Delete</button>
                        </td>
                    </tr>
            </table>
        </section>
    </main>
          
</template>

<script setup>

    // props recebida pelo componente pai (App), Tasks é um array com todas as tarefas adicionadas
    const props = defineProps(['tasks'])
    // funcao recebida pelo componente pai (App)
    const emit = defineEmits(['renderTask'])
</script>


<style scoped>
.texto{
    max-width: 700px;
    max-width: 100px;
}
main{
    display: flex;
    flex-direction: row;
}
#task-item{
    width: 100%;
    display: flex;
    border-radius: 5px;
   
    box-shadow: rgba(100, 100, 111, 0.2) 4px 4px 50px 10px;
}
#task-actions{
    display: flex;
    gap: 3px;
    height: 100px;
    justify-items: center;
}
button{
    margin: 3px;
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
#edit{
    background-color: #ff9b05;
}
#edit:hover{
    background-color: #ff9f10;
}
#delete{
    background-color: #ff1500;
}
#delete:hover{
    background-color: #ff5647;
}
</style>