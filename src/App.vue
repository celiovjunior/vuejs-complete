<template>
    <div id="app">
        <h1>Carros</h1>
        <ul>
            <li v-for="(carro, k) in carrosAzuis" :key="k">{{ carro.marca }}</li>
        </ul>
        <button @click="removerCarro">Remover</button>        
        <p>{{ contador }}</p>
        <button @click="adicionar">Adicionar</button>
    </div>
</template>

<script>

export default {
    name: '#app',
    data() {
        return {
            contador: 0,
            carros: [
            {
                marca: 'vw',
                cor: 'azul'
            },
            {
                marca: 'ford',
                cor: 'preto'
            },
            {
                marca: 'tesla',
                cor: 'azul'
            }
            ]
        }
    },
    computed: {
        carrosAzuis() {
            const filtro = this.carros.filter(({cor}) => cor === 'azul');
            return filtro
        }
    },
    methods: {
        removerCarro() {
            this.carros.pop()
        },
        adicionar() {
            this.contador++
        }
    },
    watch: {
        carros(valorNovo) {
            console.log(valorNovo)
        }
    }
}
</script>

<style>

</style>
