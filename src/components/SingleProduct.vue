<template>
  <p>Item id: {{productInfo.id}}</p>
</template>

<script>
export default {
  name: "SingleProduct",
  props: {
    productInfo: Object
  }
}
</script>

<style scoped>
p {
  background: #42b983;
  width: 100px;
  padding: 1em;
}
</style>