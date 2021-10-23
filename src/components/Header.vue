<template>
    <header class="header">
        <span>Lista de Tarefas do {{ nome }}</span>
    </header>
</template>

<script>
export default {
    props: ['nome']
}
</script>

<style>
.header {
    text-align: center;
    background: lightgreen;
    padding: 30px 0;
    font-size: 1.5em;
}
</style>