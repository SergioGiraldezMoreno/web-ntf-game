<template>
    <div>
        <div ref="node" class="roadmap-stage-div trans justify-content-center d-flex flex-column p-3 mx-auto"
            @mouseover="hover = true"
            @mouseleave="hover = false"
            :style="{height: getNodeHeight}">
            <h2 class="display-6 fw-bold yellow-text">{{ title }}</h2>
            <h5 class="yellow-text fw-bold">{{ date_title }}</h5>
            <p v-if="hover" class="mb-auto">
                {{ content }}
            </p>
        </div>
    </div>
</template>

<script>
export default {
    name: "RoadmapNode",
    props: {
        title: String,
        date_title: String,
        content: String,
    },
    data() {
        return {
            hover: false,
            nodeHeight: 0,
        }
    },
    mounted() {
        window.addEventListener('resize', this.updateNodeHeight);
        this.updateNodeHeight();
    },
    unmounted() {
        window.removeEventListener('resize', this.updateNodeHeight);
    },
    methods: {
        updateNodeHeight() {
            var node = this.$refs['node'];
            if (node == null) {
                return 0
            }
            let nodeWidth = this.$refs.node.clientWidth;
            this.nodeHeight = nodeWidth;
        }
    },
    computed :{
        getNodeHeight() {
            if (this.hover){
                return "auto";
            } else {
                return this.nodeHeight + 'px';
            }
        }
    }
};
</script>

<style scoped>

.roadmap-stage-div{
    box-shadow: 0 0 10px grey;
    background-image: linear-gradient(to right, rgba(10, 10, 10, 0.75), rgb(43, 43, 43, 0.75) 98%);
    border: solid 4px rgb(37, 36, 22);
    width: 100%;
    max-width: 50vw;
    max-height: 50vw;
    border-radius: 100%;
    overflow: hidden;
}
.roadmap-stage-div:hover{
    background-image: linear-gradient(to right, rgba(10, 10, 10, 0.85), rgb(43, 43, 43, 0.85) 98%);
    border-radius: 0px;
    width: 120%;
    height: auto;
    max-height: none;
    position: relative;
    left: -4%;
}
.trans {
    -webkit-transition: border-radius .15s;
    transition: border-radius .15s;
}
@media screen and (max-width: 767px) {
    .roadmap-stage-div{
        width: 95%;
        max-width: 60vw;
        max-height: 60vw;
    }
    .roadmap-stage-div:hover{
        width: 100%;
        position: relative;
        left: 0px;
    }
}
</style>