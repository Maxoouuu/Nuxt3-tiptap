<template>
    <p>Exemple 1 sans br</p>
    <span v-html="texte"></span>

    <p>Exemple 2 avec br</p>
    <span v-html="texte.replace(/<p><\/p>/g, '<br />')"></span>
</template>

<script setup>
const texte = "<p>a</p><p>a</p><p></p><p>a</p>"
</script>