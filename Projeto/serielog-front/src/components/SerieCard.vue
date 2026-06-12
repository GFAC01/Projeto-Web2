<script setup>
const props = defineProps({ serie: Object })

const emit = defineEmits(['remover'])

function removerSerie() { 
    emit('remover', props.serie.id)
}

</script>

<template>
    <div class="cardSerie">

        <h2> {{ serie.titulo }} </h2>

        <p>Gênero: {{ serie.genero }} </p>

        <p>Nota: {{ serie.nota }} </p>

        <p>Ano: {{ serie.ano }} </p>

        <p> {{ serie.assistida ? 'Assistida' : 'Não Assistida' }} </p>

        <button @click="removerSerie" class="btn-remover"> Remover </button>

    </div>
</template>
