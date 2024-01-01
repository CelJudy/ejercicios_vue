<script setup>
    const listaFrutas=["manzana", "platano", "pera", "naranja"];
    const frutas={"fav":"uva","dulce":"dirazno", "acida":"fresa"};
    const arrayFrutas=[
        {
            name: "manzana",
            price: 5,
            descripcion: "es roja",
            stock:0,
        },
        {
            name: "platano",
            price: 2,
            descripcion: "es amarilla",
            stock:10,
        }
    ];
</script>

<template>
    <ul>
        <li v-for="fruta in listaFrutas">{{ fruta }}</li><!--la etiqueta se repite mientras recorre el arreglo-->
        <!--en vanilla javascript "for in" es para arreglos y "for of" para objetos, en vue js "for in" y "for of" funciona para arreglos y objetos-->
    </ul>



    <ul>
        <li v-for="(fruta, index) in listaFrutas">{{index}} - {{ fruta }}</li><!--imprimir arreglo con posicion-->
    </ul>



    <ul>
        <li v-for="(valor, llave, index) in frutas">{{index}} - {{llave}} - {{ fruta }}</li>
        <!--imprimir objeto con index (posicion)  llave(caracteristica) y valor(fruta)-->
    </ul>


    <ul>
        <li v-for="fruta in arrayFrutas" :key="fruta.name">Fruta:{{ fruta.name }} - Precio:{{ fruta.price }} Descripcion:{{ fruta.descripcion }}</li>
        <!-- :key deve recibir un elemento unico y es usado para indicar que sera una llave -->
    </ul>

    <!--  v.for con v-if -->
    <ul>
        <div v-for="fruta in arrayFrutas" :key="fruta.name">
            <li v-if="fruta.stock > 0">
                    Fruta:{{ fruta.name }} - Precio:{{ fruta.price }} Descripcion:{{ fruta.descripcion }}
            </li>
        </div>
    </ul>
</template>