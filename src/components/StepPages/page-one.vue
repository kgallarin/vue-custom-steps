<template>
  <div class="page" ref="pageOne">
    Hello I am first step.
  </div>
</template>

<script>
export default {
  name: 'PageOne',
  methods: {
    validate() {      
      return true
    }
  },
  mounted() {
    this.$emit('on-validated', true)
  }
}
</script>