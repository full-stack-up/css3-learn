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
                  style="stroke:rgb(255,0,0);stroke-width:2"/>

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
        <div ref="icon1" class="icon1" @mouseenter="over($event)" @mouseleave="leave($event)"></div>
        <div ref="icon2" class="icon2" @mouseenter="over($event)" @mouseleave="leave($event)"></div>
        <div ref="icon3" class="icon3" @mouseenter="over($event)" @mouseleave="leave($event)"></div>
        <div ref="icon3Sub" class="icon3Sub" @mouseenter="over($event)" @mouseleave="leave($event)"></div>
        <div ref="icon4" class="icon4" @mouseenter="over($event)" @mouseleave="leave($event)"></div>
        <div ref="icon4Sub" class="icon4Sub" @mouseenter="over($event)" @mouseleave="leave($event)"></div>
        <div ref="icon5" class="icon5" @mouseenter="over($event)" @mouseleave="leave($event)"></div>
        <div ref="icon6" class="icon6" @mouseenter="over($event)" @mouseleave="leave($event)"></div>
        <div ref="icon7" class="icon7" @mouseenter="over($event)" @mouseleave="leave($event)"></div>
        <div ref="icon8" class="icon8" @mouseenter="over($event)" @mouseleave="leave($event)"></div>
        <div ref="icon9" class="icon9" @mouseenter="over($event)" @mouseleave="leave($event)"></div>
        <div ref="icon10" class="icon10" @mouseenter="over($event)" @mouseleave="leave($event)"></div>
        <div ref="toolTip"
             style="display: none;width: 100px;height: 100px; background-color: red;position: absolute"></div>

    </div>
</template>

<script>

export default {
    name: 'FlowChart',
    components: {},
    mounted() {
        //使最底下的图标开始移动
        this.start();

        //监听每个图标到达终点后的事件，并发出广播
        this.listening();

        //监听从中间向顶部移动的广播
        this.$eventHub.$on('leftPart-center-to-top',()=>{
            this.$refs.icon1.style.display = "block"
            this.$refs.icon1.style.animationPlayState = "running"
        });
        this.$eventHub.$on('rightPart-center-to-top',()=>{
            this.$refs.icon3.style.display = "block"
            this.$refs.icon3.style.animationPlayState = "running"
        });
        this.$eventHub.$on('rightPart-center-to-top-middleIcon',()=>{
            this.$refs.icon3Sub.style.display = "block"
            this.$refs.icon3Sub.style.animationPlayState = "running"
        })

        //监听从顶部向中间移动的广播
        this.$eventHub.$on('leftPart-top-to-center',()=>{
            this.$refs.icon2.style.display = "block"
            this.$refs.icon2.style.animationPlayState = "running"
        })
        this.$eventHub.$on('rightPart-top-to-center',()=>{
            this.$refs.icon4.style.display = "block"
            this.$refs.icon4.style.animationPlayState = "running"
        })
        this.$eventHub.$on('rightPart-top-to-center-middleIcon',()=>{
            this.$refs.icon4Sub.style.display = "block"
            this.$refs.icon4Sub.style.animationPlayState = "running"
        })

        //监听从中间向底部移动的广播
        this.$eventHub.$on('leftPart-center-to-bottom',()=>{
            this.$refs.icon5.style.display = "block"
            this.$refs.icon5.style.animationPlayState = "running"
        })
        this.$eventHub.$on('rightPart-center-to-bottom',()=>{
            this.$refs.icon9.style.display = "block"
            this.$refs.icon9.style.animationPlayState = "running"
        })
        this.$eventHub.$on('rightPart-center-to-bottom-middleIcon',()=>{
            this.$refs.icon7.style.display = "block"
            this.$refs.icon7.style.animationPlayState = "running"
        })

        //监听循环一遍后图标重新开始的位置
        this.$eventHub.$on('leftPart-start',()=>{
            this.$refs.icon6.style.display = "block"
            this.$refs.icon6.style.animationPlayState = "running"
        })
        this.$eventHub.$on('middlePart-start',()=>{
            this.$refs.icon8.style.display = "block"
            this.$refs.icon8.style.animationPlayState = "running"
        })
        this.$eventHub.$on('rightPart-start',()=>{
            this.$refs.icon10.style.display = "block"
            this.$refs.icon10.style.animationPlayState = "running"
        })
    },
    data() {
        return {}
    },
    methods: {
        getMousePos(event) {
            let e = event
            let scrollX = document.documentElement.scrollLeft || document.body.scrollLeft;
            let scrollY = document.documentElement.scrollTop || document.body.scrollTop;
            let x = e.pageX || e.clientX + scrollX;
            let y = e.pageY || e.clientY + scrollY;
            //	    return { 'x': x, 'y': y };
            console.log({'x': x, 'y': y});
        },

        over(event) {
            const eventDom = event.target;
            eventDom.style.animationPlayState = "paused";


            //获取鼠标停止时候的坐标
            let e = event;
            let scrollX = document.documentElement.scrollLeft || document.body.scrollLeft;
            let scrollY = document.documentElement.scrollTop || document.body.scrollTop;
            let x = e.pageX || e.clientX + scrollX;
            let y = e.pageY || e.clientY + scrollY;
            console.log({'x': x, 'y': y});

            this.$refs.toolTip.style.display = "block";
            this.$refs.toolTip.style.left = (x - 400) + "px";
            this.$refs.toolTip.style.top = (y - 200) + "px";
        },
        leave(event) {
            const eventDom = event.target;
            eventDom.style.animationPlayState = "running";
            this.$refs.toolTip.style.display = "none";

        },
        start() {
            this.$refs.icon6.style.display = "block"
            this.$refs.icon6.style.animationPlayState = "running"

            this.$refs.icon8.style.display = "block"
            this.$refs.icon8.style.animationPlayState = "running"

            this.$refs.icon10.style.display = "block"
            this.$refs.icon10.style.animationPlayState = "running"
        },
        listening() {
            this.bottomToCenter();
            this.centerToTop();
            this.topToCenter();
            this.centerToBottom();
        },
        bottomToCenter() {
            //图标从底下往中间移动
            this.$refs.icon6.addEventListener('animationend', () => {
                // console.log('icon6 finished animating!');
                this.$refs.icon6.style.display = 'none'
                this.$eventHub.$emit("leftPart-center-to-top");
            });
            this.$refs.icon8.addEventListener('animationend', () => {
                // console.log('icon8 finished animating!');
                this.$refs.icon8.style.display = 'none'
                this.$eventHub.$emit("rightPart-center-to-top-middleIcon");

            });
            this.$refs.icon10.addEventListener('animationend', () => {
                // console.log('icon10 finished animating!');
                this.$refs.icon10.style.display = 'none'
                this.$eventHub.$emit("rightPart-center-to-top");

            });

        },
        centerToTop() {
            //图标从中间往顶部移动
            this.$refs.icon1.addEventListener('animationend', () => {
                this.$eventHub.$emit("leftPart-top-to-center");
                // console.log('icon1 finished animating!');
                this.$refs.icon1.style.display = 'none'
            });
            this.$refs.icon3.addEventListener('animationend', () => {
                // console.log('icon3 finished animating!');
                this.$eventHub.$emit("rightPart-top-to-center");
                this.$refs.icon3.style.display = 'none'
            });
            this.$refs.icon3Sub.addEventListener('animationend', () => {
                this.$eventHub.$emit("rightPart-top-to-center-middleIcon");
                // console.log('icon3Sub finished animating!');
                this.$refs.icon3Sub.style.display = 'none'
            });
        },
        topToCenter() {
            //图标从顶部往中间移动
            this.$refs.icon2.addEventListener('animationend', () => {
                this.$eventHub.$emit("leftPart-center-to-bottom");
                // console.log('icon2 finished animating!');
                this.$refs.icon2.style.display = 'none'
            });
            this.$refs.icon4.addEventListener('animationend', () => {
                this.$eventHub.$emit("rightPart-center-to-bottom");
                // console.log('icon4 finished animating!');
                this.$refs.icon4.style.display = 'none'
            });
            this.$refs.icon4Sub.addEventListener('animationend', () => {
                this.$eventHub.$emit("rightPart-center-to-bottom-middleIcon");
                // console.log('icon4Sub finished animating!');
                this.$refs.icon4Sub.style.display = 'none'
            });
        },
        centerToBottom() {
            //图标从中间往底部移动
            this.$refs.icon5.addEventListener('animationend', () => {
                this.$eventHub.$emit("leftPart-start");
                // console.log('icon5 finished animating!');
                this.$refs.icon5.style.display = 'none'
            });
            this.$refs.icon7.addEventListener('animationend', () => {
                // console.log('icon7 finished animating!');
                this.$eventHub.$emit("middlePart-start");
                this.$refs.icon7.style.display = 'none'
            });

            this.$refs.icon9.addEventListener('animationend', () => {
                this.$eventHub.$emit("rightPart-start");
                // console.log('icon9 finished animating!');
                this.$refs.icon9.style.display = 'none'
            });
        }
    }
}
</script>

<style lang="stylus" scoped>

.home
    position absolute
    left 400px;
    top 200px;
    width 600px
    height 600px
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
    display none
    position absolute
    left 140px
    top 110px
    width: 24px;
    height: 24px;
    background-image: url("../../image/qiqiu.png")
    background-repeat: no-repeat
    offset-path: path('M0 122 L0 40');
    offset-distance: 0%;
    animation: run-line 5s linear 1 paused;

.icon2
    display none
    position absolute
    left 160px;
    top 110px;
    width: 24px;
    height: 24px;
    background-image: url("../../image/qiqiu.png")
    background-repeat: no-repeat
    offset-path: path('M0 40 L0 123');
    offset-distance: 0%;
    animation: run-line 5s linear 1 paused;


.icon3
    display none
    position absolute
    right 135px;
    top 110px;
    width: 24px;
    height: 24px;
    background-image: url("../../image/quanquan.png")
    background-repeat: no-repeat
    offset-path: path('M0 122 L0 40');
    offset-distance: 0%;
    animation: run-line 5s linear 1 paused;

.icon3Sub
    display none
    position absolute
    right 135px;
    top 110px;
    width: 24px;
    height: 24px;
    background-image: url("../../image/baoxincai.png")
    background-repeat: no-repeat
    offset-path: path('M0 122 L0 40');
    offset-distance: 0%;
    animation: run-line 7s linear 1 paused;

.icon4
    display none
    position absolute
    right 115px;
    top 110px;
    width: 24px;
    height: 24px;
    background-image: url("../../image/quanquan.png")
    background-repeat: no-repeat
    offset-path: path('M0 40 L0 123');
    offset-distance: 0%;
    animation: run-line 5s linear 1 paused;

.icon4Sub
    display none
    position absolute
    right 115px;
    top 110px;
    width: 24px;
    height: 24px;
    background-image: url("../../image/baoxincai.png")
    background-repeat: no-repeat
    offset-path: path('M0 40 L0 123');
    offset-distance: 0%;
    animation: run-line 5s linear 1 paused;


.icon5
    display none
    position absolute
    width: 24px;
    height: 24px;
    background-image: url("../../image/qiqiu.png")
    background-repeat: no-repeat
    offset-path: path('M240 340 L140 460');
    offset-distance: 0%;
    animation: run-line 5s linear paused;


.icon6
    display none
    position absolute
    width: 24px;
    height: 24px;
    background-image: url("../../image/qiqiu.png")
    background-repeat: no-repeat
    offset-path: path('M160 460 L260 340');
    offset-distance: 0%;
    animation: run-line 3s linear 1 paused;


.icon7
    display none
    position absolute
    left 290px;
    top 310px;
    width: 24px;
    height: 24px;
    background-image: url("../../image/baoxincai.png")
    background-repeat: no-repeat
    offset-path: path('M0 40 L0 144');
    offset-distance: 0%;
    animation: run-line 5s linear 1 paused;

.icon8
    display none
    position absolute
    left 310px;
    top 310px;
    width: 24px;
    height: 24px;
    background-image: url("../../image/baoxincai.png")
    background-repeat: no-repeat
    offset-path: path('M0 144 L0 30');
    offset-distance: 0%;
    animation: run-line 7s linear 1 paused;

.icon9
    display none
    position absolute
    width: 24px;
    height: 24px;
    background-image: url("../../image/quanquan.png")
    background-repeat: no-repeat
    offset-path: path('M350 340 L420 460');
    offset-distance: 0%;
    animation: run-line 5s linear 1 paused;


.icon10
    display none
    position absolute
    width: 24px;
    height: 24px;
    background-image: url("../../image/quanquan.png")
    background-repeat: no-repeat
    offset-path: path('M440 460 L370 340');
    offset-distance: 0%;
    animation: run-line 5s linear 1 paused;

.active
    animation-play-state: running;

.paused
    animation-play-state: paused;

</style>
