<script setup>
    import {ref, computed} from "vue";

    const contador=ref(0);
    let arreglo=ref([]);
    //let boton=ref(false);

    const cambiar = (num) => {
        contador.value=num;
        /* if(arreglo.value.indexOf(num)>=0){
            boton.value=true;
        }else{
            boton.value=false;
        } */
    }

    const cambiarColor = computed(()=>{
        if(contador.value<0){
            return "color:red";
        }else if(contador.value==0){
            return "color:black";
        }else{
            return "color:green";
        }
    });

    const boton = computed(()=>{
        const numSearch=arreglo.value.find((num)=>num===contador.value);
        return numSearch || numSearch===0;
    });

    const agregar=()=>{
        arreglo.value.push(contador.value);
        //boton.value=true;
    }
</script>

<template>
    <h2 :style="cambiarColor">{{ contador }}</h2><!-- a contador no es necesario poner .value por que vue lo toma por defecto -->

    <button @click="cambiar(contador+1)">incrementar</button> 
    <button @click="cambiar(contador-1)">disminuir</button> 
    <button @click="cambiar(0)">resetear</button>
    <button @click="agregar" :disabled="boton">agregar</button>

    <ul>
        <li v-for="numero in arreglo">{{ numero }}</li>
    </ul>
</template>