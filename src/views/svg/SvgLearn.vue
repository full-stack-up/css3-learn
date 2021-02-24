<template>
    <div class="home">
        <svg width="500px" height="500px">
            <!-- 原形-->
            <circle cx="100" cy="50" r="40" stroke="black"
                    stroke-width="2" fill="red" />
        </svg>

        <svg width="500px" height="500px">
            <!--    矩形        -->
            <rect width="300" height="100"
                  style="fill:rgb(0,0,255);stroke-width:1;stroke:rgb(0,0,0)"/>
        </svg>
        <svg width="500px" height="500px">
            <!--    圆角矩形        -->
            <rect x="50" y="20" rx="20" ry="20" width="150" height="150"
                  style="fill:red;stroke:black;stroke-width:5;opacity:0.5"/>
        </svg>

        <svg width="500px" height="500px">
            <!--    椭圆       -->
            <ellipse cx="300" cy="80" rx="100" ry="50"
                     style="fill:yellow;stroke:purple;stroke-width:2"/>
        </svg>

        <svg width="500px" height="500px">
            <!--    层叠椭圆       -->
            <ellipse cx="240" cy="100" rx="220" ry="30" style="fill:purple"/>
            <ellipse cx="220" cy="70" rx="190" ry="20" style="fill:lime"/>
            <ellipse cx="210" cy="45" rx="170" ry="15" style="fill:yellow"/>
        </svg>

        <svg width="500px" height="500px">
            <!--    同心椭圆       -->
            <ellipse cx="240" cy="50" rx="220" ry="30" style="fill:yellow"/>
            <ellipse cx="220" cy="50" rx="190" ry="20" style="fill:white"/>
        </svg>

        <svg width="500px" height="500px">
            <!--    直线       -->
            <line x1="0" y1="0" x2="200" y2="200"
                  style="stroke:rgb(255,0,0);stroke-width:2"/>
        </svg>


        <svg width="500px" height="500px">
            <!--    多边形       -->
            <polygon points="200,10 250,190 160,210"
                     style="fill:lime;stroke:purple;stroke-width:1"/>
        </svg>

        <svg width="500px" height="500px">
            <!--    点连接的折线      -->
            <polyline points="20,20 40,25 60,40 80,120 120,140 200,180"
                      style="fill:none;stroke:black;stroke-width:3" />
        </svg>

        <svg width="500px" height="500px">
            <!--    路径      -->
            <path d="M150 0 L75 200 L225 200 Z" />
        </svg>

        <svg width="500px" height="500px">
            <!--    路径画的曲线    -->
            <path d="M 100 350 q 150 -300 300 0" stroke="blue"
                  stroke-width="5" fill="none" />
        </svg>



        <svg width="500px" height="500px">
            <!--    文本    -->
            <defs>
                <path id="path1" d="M75,20 a1,1 0 0,0 100,0" />
            </defs>
            <text x="10" y="100" style="fill:red;">
                <textPath xlink:href="#path1">I love SVG I love SVG</textPath>
            </text>
        </svg>


    </div>
</template>

<script>

export default {
    name: 'CanvasOne',
    components: {},
    mounted() {
    },
    methods: {

    }
}
</script>

<style lang="stylus" scoped>


</style>
