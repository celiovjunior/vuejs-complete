<template>
    <div id="app">
        <p>Bermuda: {{ estoque }}</p>
        <button v-show="estoque" @click="Comprar">+</button>
        <button v-show="contador >= 1" @click="Remover">-</button>
        <p>Carrinho: {{ contador }}</p>
    </div>
    <template v-if="estoque <= 0">
        <p>Item esgotado.</p>
    </template>
</template>

<script>


export default {
    name: '#app',
    data() {
        return {
            contador: 0,
            estoque: 7
        }
    },
    methods: {
        Comprar() {
            this.contador++
            this.estoque--
        },
        Remover() {
            this.contador--
            this.estoque++
        }
    }
}


</script>

<style>

</style>
