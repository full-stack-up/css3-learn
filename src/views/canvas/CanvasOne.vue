<template>
    <div class="home">
        <canvas id="canvas1" width="500px" height="500px"></canvas>
    </div>
</template>

<script>

export default {
    name: 'CanvasOne',
    components: {},
    mounted() {
        this.drawCanvas();
    },
    methods: {
        drawCanvas() {
            const cns = document.getElementById('canvas1');
            const ctx = cns.getContext("2d");
            //连接线
            // ctx.moveTo(50,100);
            // ctx.lineTo(150,50);
            // ctx.lineTo(200,50);
            // ctx.lineTo(50,100);
            //
            // ctx.moveTo(300,70);
            // ctx.lineTo(310,180);
            // ctx.lineTo(320,200);
            // ctx.lineTo(320,200);
            // ctx.lineTo(230,200);
            // ctx.lineTo(300,70);
            // ctx.stroke();

            //画一个空心矩形
            // ctx.strokeStyle = "red";
            // ctx.strokeRect(50,50,100,100);


            //画一个实心矩形
            // ctx.fillStyle = "HotPink";
            // ctx.fillRect(50,50,100,100);

            //边框和实心一起画
            // ctx.strokeStyle = "black";
            // ctx.strokeRect(50,50,100,100);
            // ctx.fillStyle = "HotPink";
            // ctx.fillRect(50,50,100,100);

            //清空矩形，做同心矩形
            // ctx.fillStyle = "HotPink";
            // ctx.fillRect(50, 50, 80, 80);
            // ctx.clearRect(60, 60, 50, 50);

            //描边半圆
            // ctx.beginPath();
            // ctx.arc(80, 80, 50, 0, 180*Math.PI/180, true);
            // ctx.closePath();
            // ctx.strokeStyle = "blue";
            // ctx.stroke();

            //绘制实心圆
            ctx.beginPath();
            ctx.arc(80, 80, 50, 0, 360*Math.PI/180, true);
            ctx.closePath();
            ctx.fillStyle = "blue";
            ctx.fill();


        }

    }
}
</script>

<style lang="stylus" scoped>

</style>
