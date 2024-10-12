<template>
    <form class="formulario">
        <!-- Color de la figura -->
        <label>Color de fondo:</label>
        <input :value="estilos.backgroundColor" @input="$emit('updateEstilos', { ...estilos, backgroundColor: $event.target.value })" type="text" placeholder="Ej: darkgreen" />
        <!-- Color del texto -->
        <label>Color de texto:</label>
        <input :value="estilos.color" @input="$emit('updateEstilos', { ...estilos, color: $event.target.value })" type="text" placeholder="Ej: white, blue, red" />
        <!-- Mostrar/Ocultar texto de la figura -->
        <label>
            <input type="checkbox" :checked="mostrarTexto" @change="$emit('updateMostrarTexto', $event.target.checked)" />
            Mostrar texto
        </label>
        <!-- Radio del borde -->
        <label>Borde:</label>
        <input :value="parseInt(estilos.borderRadius)" @input="$emit('updateEstilos', { ...estilos, borderRadius: $event.target.value + 'px' })" type="range" min="0" max="100" />
        <!-- Cambiar el texto que aparece en la figura -->
        <label>Contenido textual:</label>
        <input :value="texto" @input="$emit('updateTexto', $event.target.value)" type="text" placeholder="Escribe algo" />
        <!-- Cambiar el estilo del texto, tipografia -->
        <label>Tipografía:</label>
        <select :value="estilos.fontFamily" @change="$emit('updateEstilos', { ...estilos, fontFamily: $event.target.value })">
            <option value="Arial">Arial</option>
            <option value="cursive">Cursiva</option>
            <option value="monospace">Monospace</option>
        </select>
        <!-- Activar opacidad o desactivar opacidad -->
        <label>
            <input type="checkbox" :checked="opaco" @change="$emit('updateOpaco', $event.target.checked)" />
            Opaco
        </label>
        <!-- Cambiar tamaño de texto -->
        <label>Tamaño de letra:</label>
        <div>
            <!-- Texto pequeño -->
            <input type="radio" :checked="estilos.fontSize === '12px'" @change="$emit('updateEstilos', { ...estilos, fontSize: '12px' })" value="12px" /> Pequeño
            <!-- Texto Mediano/ por defecto -->
            <input type="radio" :checked="estilos.fontSize === '16px'" @change="$emit('updateEstilos', { ...estilos, fontSize: '16px' })" value="16px" /> Mediano
            <!-- Texto Grande -->
            <input type="radio" :checked="estilos.fontSize === '24px'" @change="$emit('updateEstilos', { ...estilos, fontSize: '24px' })" value="24px" /> Grande
        </div>
    </form>
</template>

<script>
export default {
    props: ['estilos', 'mostrarTexto', 'texto', 'opaco'],
};
</script>
<style>
.formulario {
    background-color: #2F4F4F;
    padding: 20px;
    border-radius: 10px;
    color: white;
    max-width: 300px;
    font-family: Arial, sans-serif;
}

.campo {
    margin-bottom: 15px;
}

label {
    display: block;
    margin: 10px;
}

input[type="text"],
select {
    width: 100%;
    padding: 5px;
    border-radius: 4px;
    border: 1px solid #ccc;
}

input[type="checkbox"],
input[type="radio"] {
    margin-left: 10px;
}

input[type="range"] {
    width: 100%;
}

.radio-buttons {
    display: flex;
    justify-content: space-between;
}

.radio-buttons input[type="radio"] {
    margin-right: 5px;
}
</style>