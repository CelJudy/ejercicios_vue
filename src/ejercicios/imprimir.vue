<script setup>
    const name="ola k ase :v";
    const styleColor="color:blue";
    const arrayColor=["red","orange", "black", "white"];
</script>

<template>
    <h1>{{ name }}</h1><!--imprimir variable name en una etiqueta-->
    <h1>{{ name.toUpperCase() }}</h1><!--imprimir variable name con una funcion en una etiqueta-->
    <h2 v-bind:style="styleColor">soy azul</h2><!--imprimir variable styleColor en los atributos de la etiqueta-->
    <h2 :style="styleColor">soy azul (con abrev)</h2><!--en lugar de escribir v-bind: solo se escribe :-->
    <h2 :style="`color: ${arrayColor[1]}`">soy naranja</h2>
    <!--`` sirve para poner string y variables sin concatenar (como "" en PHP)-->
</template>
    