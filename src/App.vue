<template>
  <div class="main-page">
    <p>
      <input type="checkbox" v-model="isEmphasis.value" name="emphasis"> emphasis
    </p>
    <moby-dummy name="Nacho" :strong="isEmphasis.value"></moby-dummy>

  </div>
</template>

<script>
import Dummy from '@/components/Dummy'

export default {
  name: 'app',
  components: {
    'moby-dummy': Dummy
  },
  data () {
    return {
      isEmphasis: {
        type: Boolean,
        default: false
      }
    }
  }
}
</script>
