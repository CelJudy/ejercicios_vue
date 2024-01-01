<script setup>
    import {ref} from "vue"; //import para poder usar variables reactivas

    const contador=ref(0); //variable reactiva contador=0

    const incrementar = () => {
        contador.value++; //las variables reactivas son objetos
    }
</script>

<template>
    <h2>{{ contador }}</h2><!-- no es necesario poner .value por que vue lo toma por defecto -->

    <button @click="incrementar">boton</button> 
    <!-- como contador es una variable reactiva, cuando cambia, automaticamente vuelve a cargar los elementos donde se utilice-->
</template>