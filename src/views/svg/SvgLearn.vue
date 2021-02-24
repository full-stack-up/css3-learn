<template>
    <div class="home">
        <svg width="300px" height="175px" version="1.1">
            <path fill="transparent" stroke="#888888" stroke-width="1" d="M10 80 Q 77.5 10, 145 80 T 280 80"
                  class="path"></path>
        </svg>

        <div class="ball" @mouseenter="over()" @mouseleave="leave()" ref="ball"></div>
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
            ball.style.backgroundColor = "blue";
            ball.className = 'ball paused';
            console.log(ball)
        },
        leave() {
            const ball = this.$refs.ball
            ball.style.backgroundColor = "red";
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
    width: 50px;
    height: 50px;
    background-color: red;
    border-radius: 50%;
    offset-path: path('M10 80 Q 77.5 10, 145 80 T 280 80');
    offset-distance: 0%;
    animation: red-ball 2s linear alternate infinite;


@keyframes red-ball {
    from {
        offset-distance: 0%;
    }
    to {
        offset-distance: 100%;
    }
}

.active
    animation-play-state: running;

.paused
    animation-play-state: paused;


</style>
