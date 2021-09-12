<template>
    <div id="app">
        <ModalAlerta>
            <template v-slot:header>
                <h1>Header do Slot</h1>
            </template>
            <template v-slot="user">
            {{ user.nome }}
            <button>Comprar</button>
            </template>
            <template v-slot:footer>
                <p>Esse é o footer do slot.</p>
            </template>
        </ModalAlerta>
    </div>
</template>

<script>

import ModalAlerta from './components/ModalAlerta.vue'

export default {
    name: '#app',
    components: {
        ModalAlerta
    }

}


</script>

<style>

</style>
