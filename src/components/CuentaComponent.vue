<template>
  <div>
      <h2>Tipo de cuenta: {{ cuenta }}</h2>
      <h2>Saldo: {{ saldo }}</h2>
      <h2>Cuenta {{ estado ? 'Activa' : 'Inactiva' }}</h2>
      <div v-for="(servicio, index) in servicios" :key="index.id">
            {{ index + 1}} - {{ servicio }}
      </div>
      <accion-saldo 
        texto='Aumentar Saldo'
        @accion="aumentar"
        />
      <accion-saldo 
        texto='Disminuir Saldo' 
        @accion="disminuir"
        :desactivar="desactivar"
        />
  </div>
</template>

<script>
import AccionSaldo from './AccionSaldo.vue';
export default {
  components: { AccionSaldo },
    name: 'CuentaComponent',
    data() {
        return {
            saldo: 1000,
            cuenta: 'Visa',
            estado: true,
            servicios: ['Giro', 'Abono', 'Transferencia'],
            desactivar: false
        }
    },
    methods: {
        aumentar(){
            this.saldo = this.saldo + 100;
            this.desactivar = false; 
        },
        disminuir(){
            if (this.saldo === 0) {
                this.desactivar = true;
                alert('Has llegado al limite');
                return
            } else {
                  this.saldo = this.saldo - 100;
            }
          
        }
    },

}
</script>

<style>

</style>