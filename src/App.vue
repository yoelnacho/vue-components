<template>
  <div class="main-page">
    <p>
      <input type="checkbox" v-model="isEmphasis.value" name="emphasis"> emphasis
      <br />
      <moby-dummy name="Nacho" :strong="isEmphasis.value"></moby-dummy>
    </p>

    <h3>Input component</h3>
    <h5>Normal input</h5>
    <moby-input v-model="input" />
    <small>input value: <strong>{{ input }}</strong></small>
    <h5>Validation</h5>
    <p>Reserved usernames: <br /> 'nacho' / 'nachito' / 'nachex'</p>
    <moby-input
      v-model="input2"
      ph="Create new user"
    />
    <h5>Emit</h5>
    <moby-input
      v-model="input2"
      ph="Fill using 5 characters"
      @applied="message()"
    />

  </div>
</template>

<script>
import Dummy from '@/components/Dummy'
import Input from '@/components/Input'

export default {
  name: 'app',
  components: {
    'moby-dummy': Dummy,
    'moby-input': Input
  },
  data () {
    return {
      isEmphasis: {
        type: Boolean,
        default: false
      },
      input: '',
      input2: ''
    }
  },
  methods: {
    message () {
      alert('Excelente!')
    }
  }
}
</script>
