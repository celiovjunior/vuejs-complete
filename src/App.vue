<template>
    <div id="app">
        <div>
            <h1>
            {{ apple.companyName }}
            </h1>
            <p :class="apple.marketCap > google.marketCap ? 'verde' : 'vermelho' ">{{ apple.marketCap}}</p>
        </div>
        <div>
            <h1>
            {{ google.companyName }}
            </h1>
            <p :class="google.marketCap > apple.marketCap ? 'verde' : 'vermelho' ">{{ google.marketCap }}</p>
        </div>
        <button @click="pushData">Push</button>
    </div>     
</template>

<script>


export default {
    name: '#app',
    data() {
        return {
            google: {},
            apple: {},
        }
    },
    methods: {
        fetchGoogle() {
            fetch("https://api.origamid.dev/stock/googl/quote")
            .then(r => r.json())
            .then(google => {
                this.google = google
            })
        },
        fetchApple() {
            fetch("https://api.origamid.dev/stock/aapl/quote")
            .then(r => r.json())
            .then(apple => {
                this.apple = apple
            })
        },
        pushData() {
            this.fetchGoogle();
            this.fetchApple()
        }
    }

}


</script>

<style>
    .verde {
        color: green
    }

    .vermelho {
        color: red
    }
</style>
