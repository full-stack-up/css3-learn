<template>
    <div class="root">
        <div class="normal">
            正常
        </div>
        <div class="test1">
            沿x轴旋转60度
        </div>
        <div class="test2">
            沿y轴旋转60度
        </div>
        <div class="test3">
            transition
        </div>
        <div class="test4">
            keyframes动画
        </div>
    </div>
</template>

<script>


export default {
    name: 'three-d'
}

</script>

<style lang="stylus" scoped>
@keyframes myfirst
    0%
        background: red; left:0px; top:0px;
    25%
        background: yellow; left:200px; top:0px;
    50%
        background: blue; left:200px; top:200px;
    75%
        background: green; left:0px; top:200px;
    100%
        background: red; left:0px; top:0px;

.normal
    width 100px
    height 100px
    background aqua

.test1
    width 100px
    height 100px
    background aqua
    transform rotateX(60deg)

.test2
    width 100px
    height 100px
    background aqua
    transform rotateY(60deg)

.test3
    margin-top 50px
    width 100px
    height 100px
    background aqua
    transition width 2s

    &:hover
        width 300px

.test4
    margin-top 100px
    width 100px
    height 100px
    animation: myfirst 5s;
    animation-iteration-count infinite
    position relative

</style>
