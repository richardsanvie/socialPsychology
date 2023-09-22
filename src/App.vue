<script setup>
import { reactive } from 'vue';


const estado = reactive({
  tarefas:
    [
      {
        titulo: 'Estudar ES6',
        finalizada: false,
      },
      {
        titulo: 'Estudar Sass',
        finalizada: false,
      },
      {
        titulo: 'Ir a academia',
        finalizada: true,
      }

    ]
})

function validaValor() {
  return
}
</script>

<template>
  <div class="container-fluid p-5">
    <div class="container bg-light border rounded-3 p-3">
      <h1>ListTasks</h1>
    </div>
    <div class="container p-1">
      <div class="container-fluid">
        <div class="row">
          <div class="col-5">
            <label for="tarefa" class="sr-only">Tarefa:</label>
            <input type="text" id="tarefa" class="form-control" placeholder="Tarefa">
          </div>
          <div class="col-3">
            <button type="submit" class="btn btn-primary mt-4">Adicionar</button>
          </div>
          <div class="col-4">
            <label for="filtro" class="sr-only">Filtrar:</label>
            <select id="filtro" class="form-control">
              <option value="tds">Todas tarefas</option>
              <option value="Pendentes">Pendentes</option>
              <option value="finalizadas">Finalizadas</option>
            </select>
          </div>
        </div>
      </div>
      <ul class="list-group mt-4">
        <li class="list-group-item" v-for="tarefa in estado.tarefas">
          <input type="checkbox" :checked="tarefa.finalizada" :id="tarefa.titulo" @keyup="checkado => checkado.target.click">
          <label class="ms-3" :for="tarefa.titulo">
            {{ tarefa.titulo }}
          </label>
        </li>
      </ul>

      <!-- <p class="m-2">lorem</p>
      <hr class="m-0">
      <p class="m-2">lorem</p>
      <hr class="m-0"> -->
    </div>
  </div>
</template>

<style scoped>
.done {
  text-decoration: line-through;
}
</style>
