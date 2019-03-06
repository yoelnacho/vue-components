<template>
  <div :class="{[$style.strong]: strong }">
    <slot>Hola</slot>
    {{ isNamed }}
  </div>
</template>

<script>
export default {
  name: 'Dummy',
  props: {
    name: String,
    strong: Boolean
  },
  computed: {
    isNamed () {
      return this.name ? this.name + '!!!' : ''
    }
  }
}
</script>
<style module>
.strong {
  composes: bold from "../assets/scss/utils.scss";
}
</style>
