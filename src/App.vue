<template>
    <div id="app">
        <input type="text" placeholder="cep" name="" id="" maxlength="8" v-model="cep">
        <h1>{{ cep }}</h1>
        <ul>
            <li v-for="(valor, key) in endereco" :key="key">
                {{key}} : {{valor}}
            </li>
        </ul>
    </div>
</template>

<script>

export default {
    name: '#app',
    data() {
        return {
            cep: "",
            endereco: {}
        }
    },
    watch: {
         async cep(valor) {
            if (valor.length === 8) {
                await fetch(`https://viacep.com.br/ws/${valor}/json`)
                .then(r => r.json())
                .then(r => {
                    this.endereco = r;
                })
    
                console.log(this.endereco)
            }
        }
    }
}
</script>

<style>

</style>
