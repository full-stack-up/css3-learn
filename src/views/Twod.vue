<template>
    <div class="root">
        <div class="normal">
            正常
        </div>
        <div class="test1">
            顺时针旋转30度
        </div>
        <div class="test2">
            位移
        </div>
        <div class="test3">
            放大
        </div>
    </div>
</template>

<script>


export default {
    name: 'two-d'
}

</script>

<style lang="stylus" scoped>
.normal
    width 100px
    height 100px
    background aqua
.test1
    width 100px
    height 100px
    background aqua
    transform rotate(30deg)
.test2
    width 100px
    height 100px
    background aqua
    transform translate(10px,10px)

.test3
    margin-top 50px
    width 100px
    height 100px
    background aqua
    transform scale(1.5)

</style>
