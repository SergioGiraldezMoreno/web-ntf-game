<template>
    <div class="carousel">
        <!-- REPLACE THIS BUTTONS WITH PICTURES -->
        <button @click="previousStage" class="arrow-icon"><img src="../assets/arrow-left.png"/></button>
        <button @click="nextStage" class="arrow-icon"><img src="../assets/arrow-right.png"/></button>
        <div class="w-100 py-3 row flex-nowrap overflow-hidden">
            <roadmap-node class="col-6 col-md-4 col-xl-3" v-for="stage in stages" :key="stage.id" :ref="'ref-'+stage.id"
                :title="stage.title" :date_title="stage.date" :content="stage.sumary" />
        </div>
    </div>
</template>

<script>
import RoadmapNode from "./RoadmapNode.vue";

export default {
    name: "RoadmapCarousel",
    components: {
        RoadmapNode,
    },
    data() {
        return {
            currentFirstStageShowingId: 1,
            stages: [{id: 1, title: "Stage 1", date: "2021 Q3", sumary: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat."},
                     {id: 2, title: "Stage 2", date: "2022 Q1", sumary: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat."},
                     {id: 3, title: "Stage 3", date: "2022 Q2", sumary: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat."},
                     {id: 4, title: "Stage 4", date: "2022 Q3", sumary: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat."},
                     {id: 5, title: "Stage 5", date: "2023 Q1", sumary: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat."},
                     {id: 6, title: "Stage 6", date: "2023 Q2", sumary: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat."},
                     {id: 7, title: "Stage 7", date: "2023 Q3", sumary: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat."},
            ]
        }
    },
    methods: {
        previousStage(clickEvent) {

        },
        nextStage(clickEvent) {
            var node = this.$refs['ref-' + this.currentFirstStageShowingId];
            if (this.currentFirstStageShowingId+1 <= this.stages.length) {
                this.currentFirstStageShowingId += 1
            }
            console.log('current first node:' + this.currentFirstStageShowingId)
            // NOW I NEED TO UPDATE THE CSS PROPERTY (RIGHT: ) SO THE ELEMENTS SHOWN ARE THE CORRECT ONES
        }
    }
};
</script>

<style scoped>
.carousel {
    height: 70vh;
}
.arrow-icon {
    border-radius: 100%;
    width: 45px;
    height: 45px;
}
.arrow-icon img{
    padding: 5px;
    height: 100%;
    width: auto;
}
</style>
