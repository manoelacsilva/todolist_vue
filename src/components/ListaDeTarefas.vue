<script setup>
    const propriedade = defineProps(['tarefas']);

    function tarefaMaiorQueZero() {
        return propriedade.tarefas.length > 0;
    } 
</script>

<template>
    <ul v-if="tarefaMaiorQueZero()" class="list-group mt-4">
        <li class="list-group-item" v-for="tarefa in propriedade.tarefas">
            <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada"
                :id="tarefa.titulo" type="checkbox">
            <label :class="{ done: tarefa.finalizada }" class="ms-3" :for="tarefa.titulo">
                {{ tarefa.titulo }}
            </label>
        </li>
    </ul>
    <h4 v-else>Não há tarefas referentes a este campo.</h4>
</template>

<style scoped>
    .done {
        text-decoration: line-through;
    }
</style>