<template>
    <div class="home">
        <div class="left-top">
        </div>
        <div class="right-top">
        </div>
        <div class="center">
        </div>
        <div class="left-bottom"></div>
        <div class="middle-bottom"></div>
        <div class="right-bottom"></div>
        <svg class="column-line" width="600px" height="600px" version="1.1">
            <line id="line-1" x1="140" y1="140" x2="140" y2="240"
                  style="stroke:rgb(255,0,0);stroke-width:2" @mouseenter="over()" @mouseleave="leave()"/>

            <line id="line-2" x1="160" y1="140" x2="160" y2="240"
                  style="stroke:rgb(255,0,0);stroke-width:2"/>

            <line id="line-3" x1="440" y1="140" x2="440" y2="240"
                  style="stroke:rgb(255,0,0);stroke-width:2"/>

            <line id="line-4" x1="460" y1="140" x2="460" y2="240"
                  style="stroke:rgb(255,0,0);stroke-width:2"/>

            <!-- 分割线    -->

            <line id="line-5" x1="240" y1="340" x2="140" y2="460"
                  style="stroke:rgb(255,0,0);stroke-width:2"/>

            <line id="line-6" x1="260" y1="340" x2="160" y2="460"
                  style="stroke:rgb(255,0,0);stroke-width:2"/>


            <line id="line-7" x1="290" y1="340" x2="290" y2="460"
                  style="stroke:rgb(255,0,0);stroke-width:2"/>

            <line id="line-8" x1="310" y1="340" x2="310" y2="460"
                  style="stroke:rgb(255,0,0);stroke-width:2"/>

            <line id="line-9" x1="350" y1="340" x2="420" y2="460"
                  style="stroke:rgb(255,0,0);stroke-width:2"/>

            <line id="line-10" x1="370" y1="340" x2="440" y2="460"
                  style="stroke:rgb(255,0,0);stroke-width:2"/>
        </svg>
        <div  ref="icon1" class="icon1" @mouseenter="over()" @mouseleave="leave()"></div>
        <div  ref="icon2" class="icon2" @mouseenter="over()" @mouseleave="leave()"></div>
        <div  ref="icon3" class="icon3" @mouseenter="over()" @mouseleave="leave()"></div>
        <div  ref="icon4" class="icon4" @mouseenter="over()" @mouseleave="leave()"></div>
        <div  ref="icon5" class="icon5" @mouseenter="over()" @mouseleave="leave()"></div>
        <div  ref="icon6" class="icon6" @mouseenter="over()" @mouseleave="leave()"></div>
        <div  ref="icon7" class="icon7" @mouseenter="over()" @mouseleave="leave()"></div>
        <div  ref="icon8" class="icon8" @mouseenter="over()" @mouseleave="leave()"></div>
        <div  ref="icon9" class="icon9" @mouseenter="over()" @mouseleave="leave()"></div>
        <div  ref="icon10" class="icon10" @mouseenter="over()" @mouseleave="leave()"></div>

    </div>
</template>

<script>

export default {
    name: 'FlowChart',
    components: {},
    mounted() {
    },
    methods: {
        over() {
            const icon1 = this.$refs.icon1
            icon1.className = 'icon1 paused';
            console.log(icon1)

            const icon2 = this.$refs.icon2
            icon2.className = 'icon2 paused';

        },
        leave() {
            const icon1 = this.$refs.icon1
            icon1.className = 'icon1 active';

            const icon2 = this.$refs.icon2
            icon2.className = 'icon2 active';
        }

    }
}
</script>

<style lang="stylus" scoped>



.home
    position absolute
    left 0
    right 0
    width 600px
    height 600px
    margin 0 auto
    background-color greenyellow

    .left-top
        position absolute
        left 100px
        top 100px
        width 100px
        height 40px
        background-color aqua

    .right-top
        position absolute
        right 100px
        top 100px
        width 100px
        height 40px
        background-color aqua

    .center
        position absolute
        left 100px
        top 240px
        width 400px
        height 100px
        background-color aqua


    .left-bottom
        position absolute
        left 100px
        bottom 100px
        width 100px
        height 40px
        background-color aqua


    .middle-bottom
        position absolute
        left 250px
        bottom 100px
        width 100px
        height 40px
        background-color aqua


    .right-bottom
        position absolute
        right 100px
        bottom 100px
        width 100px
        height 40px
        background-color aqua


@keyframes run-line
    from
        offset-distance: 0%;
    to
        offset-distance: 100%;

.column-line
    display block
    position: absolute;
.icon1
    position absolute
    left 140px
    top 110px
    width: 24px;
    height: 24px;
    background-image: url("../../image/flower.png")
    background-repeat: no-repeat
    offset-path: path('M0 40 L0 123');
    offset-distance: 0%;
    animation: run-line 4s linear infinite;
.icon2
    position absolute
    left 160px;
    top 110px;
    width: 24px;
    height: 24px;
    background-image: url("../../image/flower.png")
    background-repeat: no-repeat
    offset-path: path('M0 122 L0 40');
    offset-distance: 0%;
    animation: run-line 4s linear infinite;
.icon3
    position absolute
    right 135px;
    top 110px;
    width: 24px;
    height: 24px;
    background-image: url("../../image/flower.png")
    background-repeat: no-repeat
    offset-path: path('M0 40 L0 123');
    offset-distance: 0%;
    animation: run-line 4s linear infinite;

.icon4
    position absolute
    right 115px;
    top 110px;
    width: 24px;
    height: 24px;
    background-image: url("../../image/flower.png")
    background-repeat: no-repeat
    offset-path: path('M0 122 L0 40');
    offset-distance: 0%;
    animation: run-line 4s linear infinite;

.icon5
    position absolute
    width: 24px;
    height: 24px;
    background-image: url("../../image/flower.png")
    background-repeat: no-repeat
    offset-path: path('M240 340 L140 460');
    offset-distance: 0%;
    animation: run-line 4s linear infinite;


.icon6
    position absolute
    width: 24px;
    height: 24px;
    background-image: url("../../image/flower.png")
    background-repeat: no-repeat
    offset-path: path('M160 460 L260 340');
    offset-distance: 0%;
    animation: run-line 4s linear infinite;


.icon7
    position absolute
    left 290px;
    top 310px;
    width: 24px;
    height: 24px;
    background-image: url("../../image/flower.png")
    background-repeat: no-repeat
    offset-path: path('M0 40 L0 144');
    offset-distance: 0%;
    animation: run-line 4s linear infinite;

.icon8
    position absolute
    left 310px;
    top 310px;
    width: 24px;
    height: 24px;
    background-image: url("../../image/flower.png")
    background-repeat: no-repeat
    offset-path: path('M0 144 L0 40');
    offset-distance: 0%;
    animation: run-line 4s linear infinite;

//<line id="line-9" x1="350" y1="340" x2="420" y2="460"
//style="stroke:rgb(255,0,0);stroke-width:2"/>
//
//<line id="line-10" x1="370" y1="340" x2="440" y2="460"
//style="stroke:rgb(255,0,0);stroke-width:2"/>

.icon9
    position absolute
    width: 24px;
    height: 24px;
    background-image: url("../../image/flower.png")
    background-repeat: no-repeat
    offset-path: path('M350 340 L420 460');
    offset-distance: 0%;
    animation: run-line 4s linear infinite;


.icon10
    position absolute
    width: 24px;
    height: 24px;
    background-image: url("../../image/flower.png")
    background-repeat: no-repeat
    offset-path: path('M440 460 L370 340');
    offset-distance: 0%;
    animation: run-line 4s linear infinite;

.active
    animation-play-state: running;

.paused
    animation-play-state: paused;

</style>
