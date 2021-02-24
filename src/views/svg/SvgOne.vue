<template>
    <div class="home">
        <svg width="300px" height="175px" version="1.1">
            <path fill="transparent" stroke="#888888" @mouseenter="over()" @mouseleave="leave()"
                  stroke-width="1" d="M10 80 Q 77.5 10, 145 80 T 280 80"
                  class="path"></path>
        </svg>

        <div src="../../image/shortharigirl.png" class="ball" @mouseenter="over()" @mouseleave="leave()"
             ref="ball"></div>
    </div>
</template>

<script>

export default {
    name: 'CanvasOne',
    components: {},
    mounted() {
    },
    methods: {
        over() {
            const ball = this.$refs.ball
            ball.className = 'ball paused';
            console.log(ball)
        },
        leave() {
            const ball = this.$refs.ball
            ball.className = 'ball active';
        }

    }
}
</script>

<style lang="stylus" scoped>
svg
    width: 300px;
    display: block;
    position: absolute;
    display: block;

.ball
    position relative
    width: 64px;
    height: 64px;
    background-image: url("../../image/redbag.png")
    background-repeat: no-repeat
    offset-path: path('M10 80 Q 77.5 10, 145 80 T 280 80');
    offset-distance: 0%;
    animation: run-line 2s linear infinite;


@keyframes run-line
    from
        offset-distance: 0%;
    to
        offset-distance: 100%;


.active
    animation-play-state: running;

.paused
    animation-play-state: paused;


</style>
