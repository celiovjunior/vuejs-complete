<template>
    <div id="app">
        {{ message }}
        <HeaderPrincipal />
    </div>
</template>

<script>

import HeaderPrincipal from './components/HeaderPrincipal.vue'

export default {
    components: {
        HeaderPrincipal
    },
    data() {
        return {
            message: "This is a message."
        }
    }

}


</script>

<style>

</style>
