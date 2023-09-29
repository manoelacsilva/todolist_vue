<script setup>
    const propriedade = defineProps(['tarefasPendentes']);
</script>

<template>
    <header class="p-5 mb-4 mt-4 bg-light rounded-3">
        <h1>Minhas Tarefas</h1>
        <p>
            Você possui {{ propriedade.tarefasPendentes }} tarefas pendentes.
        </p>
    </header>
</template>