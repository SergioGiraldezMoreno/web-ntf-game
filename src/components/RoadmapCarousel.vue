<template>
    <div class="carousel row p-0 mx-auto">
        <div class="d-md-none col-12 my-auto">
            <button @click="previousStage" :disabled="currentFirstStageShowingId == 1" class="arrow-icon custom-button">
                <img class="pe-1" src="../assets/sharp-arrow-left.png"/>
            </button>
            <button @click="nextStage" :disabled="currentFirstStageShowingId == stages.length" class="arrow-icon custom-button mx-auto">
                <img class="ps-1" src="../assets/sharp-arrow-right.png"/>
            </button>
        </div>
        <div class="d-none d-md-block col-2 col-md-1 my-auto p-0">
            <button @click="previousStage" :disabled="currentFirstStageShowingId == 1" class="arrow-icon custom-button">
                <img class="pe-1" src="../assets/sharp-arrow-left.png"/>
            </button>
        </div>
        <div id="carousel-inner" class="overflow-hidden col-12 col-md-10 my-auto p-0">
            <!-- TODO: ADD ANIMATION WHEN MOVING!! (fade the leaving node and move the currently visible then unfade de new node)-->
            <div class="w-100 p-0 m-0 row flex-nowrap" :style="{ left: '-' + currentNodePosition + 'px' }">
                <div class="col-12 col-md-6 col-lg-4 col-xxl-3 my-auto"
                     v-for="stage in stages"
                     :key="stage.id"
                     :ref="'ref_node_'+stage.id">
                    <div id="node-container" class="row">
                        <roadmap-node class="col-12 col-md-10 p-0 my-auto" :title="stage.title" :date_title="stage.date" :content="stage.sumary" />
                        <img v-if="stage.id != stages.length" class="d-none p-0 d-md-block col-2 arrow-img-carousel my-auto" src="../assets/sharp-arrow-right.png"/>
                    </div>
                </div>
            </div>
        </div>
        <div class="d-none d-md-block col-2 col-md-1 my-auto p-0">
            <button @click="nextStage" :disabled="currentFirstStageShowingId == stages.length" class="arrow-icon custom-button mx-auto">
                <img class="ps-1" src="../assets/sharp-arrow-right.png"/>
            </button>
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
            // TODO: CONTENT
            stages: [{id: 1, title: "Stage 1", date: "2021 Q3", sumary: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat."},
                     {id: 2, title: "Stage 2", date: "2022 Q1", sumary: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat."},
                     {id: 3, title: "Stage 3", date: "2022 Q2", sumary: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat."},
                     {id: 4, title: "Stage 4", date: "2022 Q3", sumary: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat."},
                     {id: 5, title: "Stage 5", date: "2023 Q1", sumary: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat."},
                     {id: 6, title: "Stage 6", date: "2023 Q2", sumary: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat."},
                     {id: 7, title: "Stage 7", date: "2023 Q3", sumary: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat."},
                     {id: 8, title: "Future", date: "...", sumary: "Far future developments"},
            ],
            currentNodePosition: 0
        }
    },
    mounted() {
        window.addEventListener('resize', this.updateCurrentNodePosition);
        this.updateCurrentNodePosition();
    },
    unmounted() {
        window.removeEventListener('resize', this.updateCurrentNodePosition);
    },
    methods: {
        previousStage() {
            if (this.currentFirstStageShowingId > 1) {
                this.currentFirstStageShowingId -= 1
                this.updateCurrentNodePosition()
            }
        },
        nextStage() {
            if (this.currentFirstStageShowingId+1 <= this.stages.length) {
                this.currentFirstStageShowingId += 1
                this.updateCurrentNodePosition()
            }
        },
        updateCurrentNodePosition() {
            var node = this.$refs['ref_node_1'];
            if (node == null) {
                return 0
            }
            let carouselNodeWidth = this.$refs.ref_node_1.clientWidth;
            var currentPosition = (this.currentFirstStageShowingId - 1) * carouselNodeWidth;
            this.currentNodePosition = currentPosition
        }
    }
};
</script>

<style scoped>
#carousel-inner div{
    position: relative;
    z-index: 1;
}
.arrow-icon {
    border-radius: 100%;
    width: 45px;
    height: 45px;
}
.arrow-icon img{
    width: 100%;
    height: 100%;
}
.arrow-img-carousel {
    margin-top: 6vw;
    height: 5vw;
    max-height: 70px;
}
#node-container {
    left: 8px;
}
@media screen and (max-width: 1399px) {
    .arrow-img-carousel{
        margin-top: 9vw;
        height: 7vw;
    }
}
@media screen and (max-width: 991px) {
    .arrow-img-carousel{
        margin-top: 13vw;
        height: 9vw;
    }
}
@media screen and (max-width: 767px) {
    #node-container {
        left: 0px;
    }
}

</style>
