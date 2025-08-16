<script setup>
    const props = defineProps(["tarefas"])
</script>

<template>
    <ul class="list-group mt-4" v-if="tarefas.length > 0">
      <li class="list-group-item" v-for="tarefa in props.tarefas">
        <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada" :id="tarefa.titulo" type="checkbox">
        <label :class="{ done: tarefa.finalizada }" :for="tarefa.titulo" class="ms-3">
          {{ tarefa.titulo }}
        </label>
      </li>
    </ul>
    <h3 v-else class="mt-3">Não existem tarefas a serem exibidas.</h3>
</template>

<style scoped>
  .done {
    text-decoration: line-through;
  }
</style>