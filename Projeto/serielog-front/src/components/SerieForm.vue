<script setup>

    import { ref } from 'vue'

    const emits = defineEmits(['salvar'])

    const titulo = ref('')
    const genero = ref('')
    const nota = ref(0)
    const ano = ref(2026)
    const assistida = ref(false)

    function enviarFormulario() {
        emits('salvar', {
            titulo: titulo.value,
            genero: genero.value,
            nota: Number(nota.value),
            ano: Number(ano.value),
            assistida: assistida.value
        })

        titulo.value = ''
        genero.value = ''
        nota.value = 0
        ano.value = 2026
        assistida.value = false
    }

</script>

<template>

    <form @submit.prevent = "enviarFormulario" class="cardForm">

        <p>Título: <input v-model="titulo"></p>

        <p>Gênero: <input v-model="genero"></p>

        <p>Nota: <input type="number" step="0.1" v-model="nota"></p>

        <p>Ano: <input type="number" v-model="ano"></p>

        <p><input type="checkbox" v-model="assistida"> Assistida</p>

        <button type="submit" class="btn-salvar">Salvar</button>
    </form>

</template>
