<template>
    <div class="card my-5">
        <div class="card-body">
            <h5 class="card-title text-center">{{ producto.titulo }}</h5>
            <img :src="producto.imagen" width="290" height="150" alt="">
            <p class="text-center text-muted card-text display-4">$ {{ Number(producto.precio).toFixed() }}</p>
            <button @click="agregarCarro(producto)" class="btn btn-primary form-control" :disabled="estaEnCarrito">
               {{ estaEnCarrito ? 'Agregado' : 'Agregar al carrito' }}
            </button>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Producto",
        props: ['producto', 'estaEnCarrito'],
        methods:{
            agregarCarro(producto){
                // emitiendo el evento para el Padre ( #nombre del evento, #lo que le envias )
                this.$emit('agregar-carro', producto);
            }
        }
    }
</script>

<style>

</style>