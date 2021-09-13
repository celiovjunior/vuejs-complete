<template>
    <div id="app">
        <button @click="fetchData">Mostrar</button>
        <ul>
            <li v-for="(dados, k) in dataApi" :key="k">{{k}} : {{ dados }}</li>
        </ul>
    </div>
</template>

<script>

export default {
    name: '#app',
    methods: {
        fetchData() {
            fetch('https://viacep.com.br/ws/04538133/json/')
            .then(r => r.json())
            .then(r => {
                this.dataApi = r
            })
        }
    },

    data() {
        return {
            dataApi: {}
        }
    }
}
</script>

<style>

</style>
