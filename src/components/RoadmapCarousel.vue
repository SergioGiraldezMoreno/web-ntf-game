<template>
    <div class="carousel">
        <!-- TODO: REPLACE THIS BUTTONS WITH PICTURES -->
        <div id="carousel-inner" class="overflow-hidden">
            <!-- TODO: ADD ANIMATION WHEN MOVING!! (fade the leaving node and move the currently visible then unfade de new node)-->
            <button @click="previousStage" :disabled="currentFirstStageShowingId == 1" 
                class="arrow-icon"><img class="pe-2" src="../assets/arrow-left.png"/></button>
            <button @click="nextStage" :disabled="currentFirstStageShowingId == stages.length"
                class="arrow-icon"><img class="ps-2" src="../assets/arrow-right.png"/></button>
            <div class="w-100 py-3 ps-0 ps-sm-1 m-0 row flex-nowrap" :style="{ left: '-' + currentNodePosition + 'px' }">
                <div class="col-12 col-sm-6 col-md-4 col-xl-3" v-for="stage in stages" :key="stage.id" :ref="'ref_node_'+stage.id">
                    <div class="row">
                        <roadmap-node class="col-12 col-sm-10 p-0" :title="stage.title" :date_title="stage.date" :content="stage.sumary" />
                        <img v-if="stage.id != stages.length" class="d-none d-sm-block col-2 arrow-img-carousel" src="../assets/arrow-right.png"/>
                    </div>
                </div>
            </div>
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
            // TODO: GET THE STAGES FROM A FILE?
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
    created() {
        window.addEventListener('resize', this.updateCurrentNodePosition);
        this.updateCurrentNodePosition();
    },
    destroyed() {
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

.carousel {
    height: 50vh;
}
#carousel-inner div{
    position: relative;
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
.arrow-img-carousel {
    margin-top: 6vw;
    height: 5vw;
    max-height: 70px;
}
@media screen and (max-width: 1199px) {
    .arrow-img-carousel{
        margin-top: 9vw;
        height: 7vw;
    }
}
@media screen and (max-width: 767px) {
    .arrow-img-carousel{
        margin-top: 14vw;
        height: 9vw;
    }
}

</style>
