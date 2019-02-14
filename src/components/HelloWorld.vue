<template>
  <div>
    <span>{{msg}}</span>
    <div class="head"></div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.head{
  width: 100%;
  height: 110px;
  background: red;
}
</style>
