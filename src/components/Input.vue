<template>
  <div class="moby-input">
    <!-- Capturo el evento del input almacenando el valor en value -->
    <input
      type="text"
      :value="code"
      @input="updatedValue($event.target.value)"
      :placeholder="ph ? ph : 'placeholder'"
      ref="input"
    >
  </div>
</template>

<script>
/*
  VALIDACIONES:

  Puedo emitir desde el componente lógica de validación del valor del input.
  Desde el componente padre, puede disparar alguna función basándome en el tipo de validación
  Las validaciones se pueden emitir con @blur, @focus, etc

*/
export default {
  name: 'Input',
  props: ['code', 'ph'],
  data () {
    return {
      invalids: ['nacho', 'nachito', 'nachex']
    }
  },
  methods: {
    updatedValue (code) {
      /*
        Validations
      */
      // Invalid words
      if (this.invalids.includes(code)) {
        alert('El usuario "' + code + '" ya está en uso.')
        this.$refs.input.value = code = ''
      }
      // Cunple con la mínima de 5 caracteres
      if (code.length === 5) {
        this.$emit('applied')
      }

      this.$emit('input', code)
    }
  }
}
</script>

<style scoped>

</style>
