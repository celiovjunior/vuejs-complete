<template>
    <div id="app">
        <!-- <h1>USUÁRIO:</h1>
        <p>{{ nomeCompleto }}</p> -->
        <button @click="puxarPaises">Puxar</button>
        <select name="paises" id="paises" v-model="paisSelecionado">
            <option v-for="(pais, k) in paises" :key="k" :value="pais.name">
                {{pais.name}}
            </option>
        </select>
        <p>{{ capital.capital }}</p>
    </div>
</template>

<script>

export default {
    name: '#app',
    data() {
        return {
            // nome: "Matheus",
            // sobrenome: "Pinheiro"
            paises: {},
            paisSelecionado: "",
            capital: ""
        }
    },
    methods: {
        puxarPaises() {
            fetch(`https://restcountries.eu/rest/v2/all`)
            .then(r => r.json())
            .then(r => {
                this.paises = r;
            })
        }
    },
    computed: {
        // nomeCompleto() {
        //     return this.nome + " " + this.sobrenome
        // }
    },
    watch: {
        paisSelecionado(valor) {
            this.capital = this.paises.find((pais) => pais.name === valor)
        }
    }
}
</script>

<style>

</style>
