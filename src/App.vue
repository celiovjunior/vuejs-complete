<template>
    <div id="app">
        <button @click="handleClick">Click</button>
        <!-- <p>{{ contador }}</p> -->
        <button @click="ativo = !ativo">Toggle</button>
        <p v-if="ativo == true">Mostrar texto.</p>
    </div>     
</template>

<script>


export default {
    name: '#app',
    data() {
        return {
            contador: 0,
            ativo: true
        }
    },
    methods: {
        handleClick() {
            console.log(event)
        }
    }
}


</script>

<style>

</style>
