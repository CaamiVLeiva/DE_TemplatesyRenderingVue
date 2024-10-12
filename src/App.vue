<template>
    <div class="container">
        <FormularioComponent :estilos="estilos" :mostrarTexto="mostrarTexto" :texto="texto" :opaco="opaco"
            @updateEstilos="estilos = $event" @updateMostrarTexto="mostrarTexto = $event" @updateTexto="texto = $event"
            @updateOpaco="opaco = $event" />

        <FiguraComponent :estilos="estilos" :mostrarTexto="mostrarTexto" :texto="texto" :opaco="opaco" />
    </div>
</template>

<script>
import FormularioComponent from './components/FormularioComponent.vue';
import FiguraComponent from './components/FiguraComponent.vue';

export default {
    components: {
        FormularioComponent,
        FiguraComponent
    },
    data() {
        return {
            estilos: {
                backgroundColor: 'darkgreen',
                color: 'white',
                borderRadius: '25px',
                fontFamily: 'cursive',
                fontSize: '16px',
            },
            texto: 'Awesome Vue.js',
            mostrarTexto: true,
            opaco: false,
        };
    },
};
</script>

<style scoped>
.container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 40px;
}
</style>