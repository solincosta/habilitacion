<template>
    <div>
        <h4  v-for="pro in productos" :key="pro.id">
            <ProductComponent :nombre="pro.nombre"/>
        </h4>
    
    </div>
  
</template>

<script>
import { APIService } from "@/service/APIService";
import ProductComponent from '@/components/ProductComponent.vue'

export default {
name: "FacturaView",
  data() {
    return {
      productos: [],
    };
  },

  components: {
    ProductComponent
  },

  methods:{
    getProductos: function (){
        this.productos = APIService.getProductos();
        console.log(this.productos);
    }
  },

  created: function () {
    this.getProductos();
  }
}
</script>

<style>

</style>