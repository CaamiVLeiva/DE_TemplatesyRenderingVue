<template>
    <div :style="[estilos, { opacity: opaco ? 0.5 : 1 }]" class="figura">
        <span v-show="mostrarTexto">{{ texto }}</span>
    </div>
</template>

<script>
export default {
    props: ['estilos', 'mostrarTexto', 'texto', 'opaco']
};
</script>

<style scoped>
.figura {
    width: 200px;
    height: 200px;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 16px;
}
</style>
