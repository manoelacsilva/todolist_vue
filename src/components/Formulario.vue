<script setup>
    const propriedade = defineProps(['cadastraTarefa', 'tarefaTemporaria', 'trocarFiltro', 'editaTarefaTemporaria']);
</script>

<template>
    <form @submit.prevent="propriedade.cadastraTarefa">
        <div class="row">
            <div class="col">
                <input :value="propriedade.tarefaTemporaria" @change="propriedade.editaTarefaTemporaria"
                    required type="text" placeholder="Digite aqui a descrição da tarefa" class="form-control">
            </div>
            <div class="col-md-2">
                <button type="submit" class="btn btn-primary">Cadastrar</button>
            </div>
            <div class="col-md-2">
                <select @change="propriedade.trocarFiltro" class="form-control">
                    <option value="todas">Todas as tarefas</option>
                    <option value="pendentes">Tarefas pendentes</option>
                    <option value="finalizadas">Tarefas finalizadas</option>
                </select>
            </div>
        </div>
    </form>
</template>