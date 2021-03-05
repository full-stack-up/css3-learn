<template>
    <div class="home">
       <flow-chart style="width: 600px;height: 600px"></flow-chart>
    </div>
</template>

<script>
import FlowChart from "@/views/svg/FlowChart";
export default {
    name: 'Show',
    components: {
        FlowChart
    },mounted() {
        // this.$eventHub.$on('bottom-to-top',()=>{
        //    alert("李健最牛")
        // });
    }
}
</script>

<style lang="stylus" scoped>
.home
    width 100%
    height 100%
</style>
