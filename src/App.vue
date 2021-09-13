<template>
    <div id="app">
        <div v-html="link"></div>
        <p v-text="item"></p>

        <p v-once>saldo: R$ {{ total - sacado }}</p>
        <button @click="sacado += 5">sacar R$ 5</button>
        <p> {{ sacado }}</p>
        <p>novo saldo: R$ {{ total - sacado }}</p>
    </div>
</template>

<script>

export default {
    name: '#app',
    data() {
        return {
            link: "<a href='https://www.google.com'>Google</a>",
            item: "Camiseta",
            total: 150,
            sacado: 20
        }
    }
}
</script>

<style>

</style>
