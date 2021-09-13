<template>
    <div id="app">
        <ul>
            <!--O v-for aceita como parametros, nessa ordem: ELEMENTO - KEY - INDEX -->
            <!-- <li v-for="el, k, index in estados" :key="k">{{ el }} : {{ k }} : {{ index }}</li> -->

            <li v-for="(estado, k) in estados" :key="k + nome">
                <h1>{{ estado.nome }}</h1>
                <p>{{ estado.populacao }}</p>
            </li>
        </ul>
        <div>
            <ul>
                <li v-for="(n, k) in 5" :key="k">{{ n }}</li>
            </ul>
        </div>
    </div>
</template>

<script>

export default {
    name: '#app',
    data() {
        return {
            estados: {
                sp: {
                    populacao: "45 milhoes",
                    nome: "Sao Paulo"
                },
                mg: {
                    populacao: "21 milhoes",
                    nome: "Minas Gerais"
                },
                rj: {
                    populacao: "17 milhoes",
                    nome: "Rio de Janeiro"
                },
                ce: {
                    populacao: "9 milhoes",
                    nome: "Ceará"
                }
            }
        }
    }
}
</script>

<style>

</style>
