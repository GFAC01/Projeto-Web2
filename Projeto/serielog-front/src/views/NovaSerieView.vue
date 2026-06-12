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
    <h1 class="top">Nova Série</h1>
    <div class="form">
        <SerieForm @salvar="salvarSerie"/>
    </div>
    
</template>
