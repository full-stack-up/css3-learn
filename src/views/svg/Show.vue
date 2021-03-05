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
    }
}
</script>

<style lang="stylus" scoped>
.home
    width 100%
    height 100%
</style>
