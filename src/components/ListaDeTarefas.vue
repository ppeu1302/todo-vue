<script setup>
    const props = defineProps(['tarefas'])
</script>

<template>
        <h4 class="mt-4 ms-2" v-if="tarefas.length <= 0">Não há tarefas pendentes</h4>
        <ul v-else class="list-group mt-5">
        <li class="list-group-item" v-for="tarefa in props.tarefas">
        <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada" :id="tarefa.titulo" type="checkbox">
        <label class="ms-3" :class="{ done: tarefa.finalizada }" :for="tarefa.titulo">
            {{ tarefa.titulo }}
        </label>
        </li>
    </ul>
</template>
<style scoped>

    .done {
        text-decoration: line-through;
    }

</style>