<template>
  <div id="app">
    <div class="row">

      <div class="col-md-7">
        <div class="row">
          <div class="col-md-6" v-for="prod in ProductosJson" :key = "prod.id">
            <producto :producto="prod" v-on:agregar-carro="agregarProdCarro" :estaEnCarrito="estaEncarrito(prod)" >  </producto>
          </div>
        </div>
      </div>

      <div class="col-md5 my-5">
        <carrito :items="carrito" v-on:remover-item="removerProducto" v-on:pagar="pagar"></carrito>
      </div>

    </div>
  </div>
</template>

<script>
import Producto from "./components/Producto";
import ProductosJson from './productos.json';
import Carrito from './components/Carrito';


export default {
  name: 'App',
  components: {
    Producto,
    Carrito
  },
  data(){
    return{
      ProductosJson,
      carrito: []
    }
  },
  methods:{
    agregarProdCarro(producto){
      this.carrito.push(producto);
    },
    estaEncarrito( producto ){
      const item = this.carrito.find(item => item.id === producto.id);
      if (item){
        return true;
      }
      return false;
    },
    removerProducto(producto){
      this.carrito = this.carrito.filter(item => item.id != producto.id);
    },
    pagar(){
      this.carrito = [];
      alert('Venta completada');
    }
  }
}
</script>

<style>

</style>
