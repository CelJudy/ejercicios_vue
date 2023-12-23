<script setup>
    const activo=true;
    const numero=10;
    const mostrar=false;
</script>

<template>
    <h2 v-if="activo"> <!--esta etiqueta se muestra solo si la validacion es true-->
        <span>Icono</span>
        Estoy activo
    </h2>
    <h2 v-else>no estoy activo</h2> <!--NOTA: si no se usa else se puede usar v-show-->




    <h2 v-if="numero<10">soy menor a 10</h2>
    <h2 v-else-if="numero=10">soy 10</h2><!--else deben ir justo debajo de su if-->
    <h2 v-else>soy mayor a 10</h2>




    <h2 v-show="mostrar">me veo solo si mostrar es true</h2><!--si la validacion es false, la etiqueta es display:none-->

    <!--la diferencia entre v-if y v-show:
    si v-if es true simplemente no renderiza la etiqueta else y viceversa
    si v-show es false la etiqueta se hace display:none-->
</template>