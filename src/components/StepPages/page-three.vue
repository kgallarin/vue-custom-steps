<template>
  <div class="page" ref="pageThree">
    Hello I am third step. <br />
    <a href="#" @click.prevent.stop="emitValidated">click me to finish step! (optional emit <strong>on-validated</strong>)</a>
  </div>
</template>

<script>
export default {
  name: 'PageThree',
  methods: {
    validate() {      
      this.$emit("on-validated", true)
    },
    emitValidated() {
      this.$emit('on-validated', true)
    }
  }
}
</script>