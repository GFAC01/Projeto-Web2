<script setup>
    import { ref, onMounted, computed } from 'vue'
    import SerieCard from '../components/SerieCard.vue'
    import FiltroSeries from '../components/FiltroSeries.vue'

    const series = ref([])
    const filtro = ref('')

    onMounted(async () => {
        const resposta = await fetch('http://localhost:3000/series')
        series.value = await resposta.json()
    })

    async function removerSerie(id) {
        await fetch(`http://localhost:3000/series/${id}`, { method: 'DELETE' })
        series.value = series.value.filter(serie => serie.id !== id)
    }

    const seriesFiltradas = computed(() => {

        if (filtro.value === '') {
            return series.value
        }

        if (filtro.value === 'Assistidas') {
            return series.value.filter(
                serie => serie.assistida
            )
        }

        if (filtro.value === 'Não Assistidas') {
            return series.value.filter(
                serie => !serie.assistida
            )
        }

        return series.value
    })

    function aplicarFiltro(valor) {
        filtro.value = valor
    }
</script>

<template>

    <h1>Minhas Séries</h1>

    <FiltroSeries @filtrar="aplicarFiltro"/>

    <SerieCard v-for="serie in seriesFiltradas" :key="serie.id" :serie="serie" @remover="removerSerie" />

    <hr>

</template>
