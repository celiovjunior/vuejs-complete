<template>
    <div id="app">
        <p :class="comprou ? 'verde' : 'vermelho'">Comprou:</p>
    </div>
        
</template>

<script>


export default {
    name: '#app',
    data() {
        return {
            comprou: true
        }
    }

}


</script>

<style>

</style>
