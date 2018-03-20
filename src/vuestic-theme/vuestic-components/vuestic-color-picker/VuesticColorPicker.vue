<template>
</template>

<script>
  import SimpleInline from './color-picker-types/SimpleInline.vue'

  export default {
    name: 'vuestic-color-picker',

    components: {
      SimpleInline
    },

    props: {

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
