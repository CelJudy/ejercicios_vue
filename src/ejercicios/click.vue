<script setup>
    const click = () => {
        alert("ola k ase :v");
    }
    const click2 = (mensaje) => {
        alert(mensaje);
    }
</script>

<template>
    <button v-on:click="click">boton 1</button>
    <button @click="click2('ola k ase')">boton 2</button>
    <!-- @click es la abreviacion v-on:click -->
    <!-- onclick no funciona -->

    <button @click.right="click2('boton derecho')">boton 3</button>
    <!-- la accion solo se ejecita cuando se hace click con el boton derecho (right) -->
    <button @click.middle="click2('boton de en medio')"></button>
    <!-- la accion solo se ejecita cuando se hace click con el boton de en medio (middle) -->

    <button @click.right="click2('boton derecho')" @click="click2('boton izquierdo')">boton 6</button>
    <!-- este boton hara 2 cosas diferentes dependiendo del boton con el que se le haga click -->

    <button @click.right.prevent="click2('boton derecho')">boton 7</button>
    <!-- "prevent" evita que el evento haga lo que hace por defalt, en este caso evita que se habra el menu del click derecho -->
</template>