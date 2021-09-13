<template>
    <div id="app">
        <ul>
            <li v-for="(curso, index) in cursos" :key="curso">{{ curso }} {{ index }} </li>
        </ul>
    </div>
</template>

<script>

export default {
    name: '#app',
    data() {
        return {
            cursos: ["HTML", "CSS", "JavaScript", "Java", "PHP"]
        }
    }
}
</script>

<style>

</style>
