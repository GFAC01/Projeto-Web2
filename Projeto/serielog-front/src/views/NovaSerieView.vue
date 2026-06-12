<script setup>

    import SerieForm from '../components/SerieForm.vue'

    async function salvarSerie(serie) {
        await fetch('http://localhost:3000/series', {
            method: 'POST',

            headers: { 'Content-Type': 'application/json' },
            body: JSON.stringify(serie)
        })

        alert('Série Cadastrada!')
    }

</script>

<template>
    <h1>Nova Série</h1>

    <SerieForm @salvar="salvarSerie"/>
    
</template>