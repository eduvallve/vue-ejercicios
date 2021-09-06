<template>
    <div>
    <h1>Hola mundo desde saludar</h1>
    <hr>
    <enviar inline-template>
        <h2>
            Template lineal - saludar.vue
            <button>Guardar</button>
        </h2>
    </enviar>
    </div>
</template>
<script>
import button from './button.vue'
export default {
  components: { button },

}
</script>
<style scoped>

</style>