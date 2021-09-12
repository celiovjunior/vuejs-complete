<template>
    <div id="app">
        <ul>
            <li><a @click.prevent="pushAction" href="https://api.origamid.dev/stock/aapl/quote">Apple</a></li>
            <li><a @click.prevent="pushAction" href="https://api.origamid.dev/stock/googl/quote">Google</a></li>
            <li><a @click.prevent="pushAction" href="https://api.origamid.dev/stock/amzn/quote">Amazon</a></li>
            <li><a @click.prevent="pushAction" href="https://api.origamid.dev/stock/ebay/quote">Ebay</a></li>
            <li><a @click.prevent="pushAction" href="https://api.origamid.dev/stock/pypl/quote">Paypal</a></li>
        </ul>
        <div>
            <h1>{{ acao.companyName}}</h1>
            <p>Mercado: {{ acao.marketCap }}</p>
            <p>Ação: {{ acao.latestPrice }}</p>
        </div>
    </div>     
</template>

<script>


export default {
    name: '#app',
    data() {
        return {
            acao: {}
        }
    },
    methods: {
        pushAction(event) {
            const url = event.target.href
            fetch(url)
            .then(r => r.json())
            .then(r => {
                this.acao = r
                console.log(r)
            })
        }
    }
}


</script>

<style>

</style>
