<script setup>
    const name="Vue dinamico";
    const styleColor="color:blue";
</script>

<template>
    <h1>ola k ase :v</h1>
    <h2 v-bind:style="styleColor">soy azul</h2>
    <h2 :style="styleColor">soy azul (con abrev)</h2>
</template>

<style>
    h1{
        color:red;
    }
</style>
    