<script setup>

    const emit = defineEmits(['filtrar'])

    function atualizar(evento) {
        emit('filtrar', evento.target.value)
    }

</script>

<template>
    <div>

        <label>Filtrar: </label>

        <select @change="atualizar">

            <option value="">Todas</option>

            <option value="Assistidas">Assistidas</option>

            <option value="Não Assistidas">Não Assistidas</option>

        </select>
    </div>
</template>