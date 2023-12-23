<script setup>
    const listaFrutas=["manzana", "platano", "pera", "naranja"];
    const frutas={"fav":"uva","dulce":"dirazno", "acida":"fresa"};
</script>

<template>
    <ul>
        <li v-for="fruta in listaFrutas">{{ fruta }}</li><!--la etiqueta se repite mientras recorre el arreglo-->
        <!--en vanilla javascript "for in" es para arreglos y "for of" para objetos, en vue js "for in" funciona para ambos-->
    </ul>



    <ul>
        <li v-for="(fruta, index) in listaFrutas">{{index}} - {{ fruta }}</li><!--imprimir arreglo con posicion-->
    </ul>



    <ul>
        <li v-for="(valor, llave) in frutas">{{index}} - {{ fruta }}</li>
        <!--imprimir objeto con valor(fruta) y llave(caracteristica)-->
    </ul>
</template>