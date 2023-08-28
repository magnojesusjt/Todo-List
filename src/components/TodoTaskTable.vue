<template>
    <main>
        <section id="task-item">
            <table width="100%">
                    <tr>
                        <td width="50px" align="center">
                            <input type="checkbox" name="" id="">
                    </td>
                        <td padding="0px" align="center" class="texto">{{task}}</td>
                    </tr>
            </table>
        </section>
        <section id="task-actions">
            <table width="100%">
                    <tr>
                        <td padding="0px" width="200px" align="center" display="flex">
                            <button id="edit">Edit</button>
                            <button id="delete">Delete</button>
                        </td>
                    </tr>  
            </table>
        </section>
    </main>
          
</template>
<script setup>
import test from './TodoTaskInput.vue'
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
    height: 100px;
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