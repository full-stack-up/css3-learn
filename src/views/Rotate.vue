<template>
  <div class="root">
<!--    <div class="circle">-->

<!--    </div>-->
    <div class="square">
    abfcdfasdf
    </div>
  </div>
</template>



<script>

export default {
  name: 'Home',
  components: {
  }
}
</script>



<style lang="stylus" scoped>

@keyframes abc
  from
    transform: rotate(0deg);
  to
    transform: rotate(360deg);

.circle
  width 200px;
  height 200px;
  border-radius 50%;
  background-color aqua;
.square
  width 64px
  height 64px
  background-color aqua
  background url("../image/money-bar.png") no-repeat
  animation  abc 3s linear infinite

</style>
