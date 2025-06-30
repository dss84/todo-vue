<script setup>
    const props = defineProps(['tarefas'])
</script>

<template>
    <div v-if="props.tarefas.length > 0">
        <ul class="list-group mt-4">
            <li class="list-group-item" v-for="tarefa in props.tarefas" :key="tarefa.id">
                <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada" :id="tarefa.titulo" type="checkbox">
                <label :class="{ done: tarefa.finalizada }" class="ms-3" :for="tarefa.titulo">
                    {{ tarefa.titulo }}
                </label>
            </li>
        </ul>
    </div>
    <div v-else>
        <p class="mt-4">Nenhuma tarefa encontrada.</p>
    </div>
</template>

<style scoped>
    .done {
        text-decoration: line-through;
    }
</style>
