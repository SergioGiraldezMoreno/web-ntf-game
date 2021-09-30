<template>
    <div class="my-4 my-lg-0">
        <!-- <div class="trans info-box justify-content-center d-flex flex-column p-3 m-auto"
            :class="showClass" -->
        <div class="roadmap-stage-div trans info-box justify-content-center d-flex flex-column p-3 mx-auto"
            @mouseover="hover = true"
            @mouseleave="hover = false">
            <h2 class="display-6 fw-bold yellow-text">{{ title }}</h2>
            <h5 class="yellow-text fw-bold">{{ date_title }}</h5>
            <p v-if="hover || show" class="mb-auto">
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
        // show: { this is for testing (activating one node with code)
        //     type: Boolean,
        //     default: false
        // },
        // showClass: {
        //     type: String,
        //     default: "roadmap-stage-div"
        // }
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
    width: 17vw;
    height: 17vw;
    border-radius: 100%;
    overflow: hidden;
}
/* .showdiv {
    border-radius: 0px;
    width: 95%;
    height: auto;
} */
.roadmap-stage-div:hover{
    border-radius: 0px;
    width: 95%;
    height: auto;
}
.trans {
    -webkit-transition: border-radius .15s;
    transition: border-radius .15s;
}
@media screen and (max-width: 1199px) {
    .roadmap-stage-div{
        width: 25vw;
        height: 25vw;
    }
}
@media screen and (max-width: 767px) {
    .roadmap-stage-div{
        width: 35vw;
        height: 35vw;
    }
}
</style>