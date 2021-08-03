<template>
  <div>
    counter value is {{ counter }}
  </div>
</template>

<script>
export default {
  props: {
    // counter: Number
    counter: {
      type: Number,
      required: true
    }
  }
}
</script>

<style scoped>

</style>