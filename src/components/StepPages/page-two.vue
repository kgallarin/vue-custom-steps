<template>
  <div class="page" ref="pageTwo">
    Hello I am second step.
  </div>
</template>

<script>
export default {
  name: 'PageTwo',
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