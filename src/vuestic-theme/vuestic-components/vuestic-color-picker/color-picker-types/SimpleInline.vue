<template>
  <compact-picker
    :value="colorObject"
    @input="change"
  >
  </compact-picker>
</template>

<script>
  import { Compact as CompactPicker } from 'vue-color'

  export default {
    name: 'simple-inline',

    components: {
      CompactPicker
    },

    props: {
      value: {
        type: String,
        required: true
      }
    },

    data () {
    },

    computed: {
      colorObject () {
        return {
          hex: this.value
        }
      }
    },

    methods: {
      change (value) {
        this.$emit('input', value.hex)
      }
    }
  }
</script>

<style lang="scss">
</style>
