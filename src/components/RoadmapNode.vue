<template>
    <div>
        <div class="roadmap-stage-div trans justify-content-center d-flex flex-column p-3 mx-auto"
            @mouseover="hover = true"
            @mouseleave="hover = false">
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
        }
    }
};
</script>

<style scoped>

.roadmap-stage-div{    
    box-shadow: 0 0 10px grey;
    background-image: linear-gradient(to right, rgba(10, 10, 10, 0.75), rgb(43, 43, 43, 0.75) 98%);
    border: solid 4px rgb(37, 36, 22);
    width: 17vw;
    height: 17vw;
    min-height: 17vw;
    border-radius: 100%;
    overflow: hidden;
}
.roadmap-stage-div:hover{
    border-radius: 0px;
    width: 95%;
    height: auto;
}
.trans {
    -webkit-transition: border-radius .15s;
    transition: border-radius .15s;
}
@media screen and (max-width: 1399px) {
    .roadmap-stage-div{
        width: 25vw;
        height: 25vw;
    }
}
@media screen and (max-width: 991px) {
    .roadmap-stage-div{
        width: 35vw;
        height: 35vw;
    }
}
/* TODO: FIX LANDSCAPE MODE SIZES */
@media screen and (max-width: 767px) {
    .roadmap-stage-div{
        width: 55vw;
        height: 55vw;
    }
}
</style>