<script setup>
    import {ref, computed} from "vue"; //import para poder usar variables reactivas y propiedades computadas

    const contador=ref(0);
    let styleColor="color:black";

    const cambiarColor = () => { //funcion, no se puede usar como variable, por lo que hay que usar otra valiable que cambia (styleColor)
        if(contador.value<0){
            styleColor="color:red";
        }else if(contador.value==0){
            styleColor="color:black";
        }else{
            styleColor="color:green";
        }
    }

    const incrementar = () => {
        contador.value++; 
        cambiarColor();
    }

    const disminuir = () => {
        contador.value--; 
        cambiarColor();
    }

    const resetear = () => {
        contador.value=0; 
        styleColor="color:black";
    }

    const color = computed(()=>{//como es computada, aunque es una funcion se puede usar como variable
        if(contador.value<0){
            return "color:red";
        }else if(contador.value==0){
            return "color:black";
        }else{
            return "color:green";
        }
    });


</script>

<template>
    <h2 :style="styleColor">{{ contador }}</h2>

    <h2 :style="color">{{ contador }}</h2>

    <button @click="incrementar">incrementar</button> 
    <button @click="disminuir">disminuir</button> 
    <button @click="resetear">resetear</button> 
</template>