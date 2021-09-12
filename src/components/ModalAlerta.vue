<template>
    <div class="modal">
       <!-- slot = posicionamento do conteúdo que será definido no App -->
        <header>
            <slot name="header"></slot>
            <h1>{{ user.nome }}</h1>
        </header>

            <slot :user="user">Fallback se não tiver conteúdo.</slot>

        <footer>
            <slot name="footer"></slot>
        </footer>
    </div>
</template>

<script>
    export default {
        name: 'ModalAlerta',
        data() {
            return {
                user: {
                    nome: "Célio"
                }
            }
        }
    }
</script>

<style>


</style>