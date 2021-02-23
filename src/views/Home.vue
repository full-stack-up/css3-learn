<template>
    <div class="home">
        <div class="example1">
            圆角
        </div>
        <div class="example2">
            边框
        </div>
        <div class="example3">
            由上而下渐变
        </div>
        <div class="example4">
            由左往右渐变
        </div>
        <div class="example5">
            对角渐变
        </div>
        <div class="example6">
            透明度渐变
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
.example1
    width 100px
    height 100px
    background-color aqua
    border-radius 10px 20px
    box-shadow 5px 5px 5px #888888

    &:hover
        box-shadow 10px 10px 5px #888888

.example2
    width 100px
    height 100px
    border: 10px dotted black;
    padding: 35px;
    background: yellow;
    background-clip: padding-box;

.example3
    width 100px
    height 100px
    background-image: linear-gradient(#e66465, #9198e5);

.example4
    width 200px;
    height: 200px;
    background-image: linear-gradient(to right, red , yellow);
    &:hover
        background-image: linear-gradient(to right, red,orange,yellow,green,blue,indigo,violet);

.example5
    width 200px;
    height: 200px;
    background-image: linear-gradient(to bottom  right, red , yellow);

.example6
    width 200px;
    height: 200px;
    background-image: linear-gradient(to right, rgba(255,0,0,0), rgba(255,0,0,1));
</style>
