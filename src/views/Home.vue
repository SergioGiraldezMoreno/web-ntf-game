<template>
    <div id="parent-div" class="main-background m-0 p-3 min-vh-100">
        <!-- TODO: hacer que parpadee (cambios entre transparete y blanco) -->
        <div v-if="isWindowTop" id="scroll-down-div" class="text-center">
            <div class="d-flex justify-content-center">
                <p class="mx-2 my-auto fs-4 fw-bold text-white">SCROLL</p>
                <img id="scroll-down-img" src="../assets/scroll_arrows.png" alt="">
                <p class="mx-2 my-auto fs-4 fw-bold text-white">DOWN</p>
            </div>
        </div>
        <!-- REMEMBER! WALLPAPER LINK! -->
        <!-- https://www.wallpaperflare.com/grim-reaper-standing-on-cliff-digital-wallpaper-landscape-digital-art-wallpaper-uyw/download/1920x1080 -->
        <div class="main-div row text-white h-100 d-flex align-items-start text-center">
            <div>
                <!-- MOBILE -->
                <div class="d-lg-none px-1 d-flex flex-column min-vh-100">
                    <img  class="m-auto magus-img-title" src="../assets/magus-light.png" alt="">
                    <router-link to="/game" class="w-75 mx-auto ">
                        <button class="custom-button mb-1 w-100 rounded-3 py-1 fs-3 fw-bold">PLAY NOW</button>
                    </router-link>
                    <router-link to="/game" class="mb-auto w-75 mx-auto ">
                        <button class="custom-button mt-1 w-100 rounded-3 py-1 fs-3 fw-bold">GET STARTED</button>
                    </router-link>
                </div>
                <!-- > MD SCREEN -->
                <div class="d-none d-lg-block row pt-5">
                    <div class="m-auto row vh-100 d-flex flex-column justify-content-center">
                        <div class="row justify-content-center">
                            <img class="mx-auto magus-img-title" src="../assets/magus.png" alt="">
                        </div>
                        <div class="row justify-content-center">
                            <router-link class="me-1 col-3" to="/game">
                                <button class="custom-button rounded-3 p-2 w-100 fs-3 fw-bold">PLAY NOW</button>
                            </router-link>
                            <router-link class="ms-1 col-3" to="/game">
                                <button class="custom-button rounded-3 w-100 p-2 fs-3 fw-bold">GET STARTED</button>
                            </router-link>
                        </div>
                    </div>
                </div>

                <div class="row equal row-cols-1 row-cols-lg-3 justify-content-center my-5">
                    <div class="col my-4 my-lg-0">
                        <div class="info-box h-100 justify-content-center m-auto d-flex flex-column" style="width: 90%">
                            <a class="p-4 d-block w-100 h-100 text-decoration-none text-white" href="#whitepaper-info">
                                <h2 class="yellow-text">Whitepaper</h2>
                                <p class="mb-auto">All you need to know about the project. The technologies, game dynamics, goals...</p>
                            </a>
                        </div>
                    </div>
                    <div class="col my-4 my-lg-0">
                        <div class="info-box h-100 justify-content-center m-auto d-flex flex-column" style="width: 90%">
                            <a class="p-4 d-block w-100 h-100 text-decoration-none text-white" href="#roadmap-info">
                                <h2 class="yellow-text">Roadmap</h2>
                                <p class="mb-auto">All the information about stages, deadlines and the current status of the project</p>
                            </a>
                        </div>
                    </div>
                    <div class="col my-4 my-lg-0">
                        <div class="info-box h-100 justify-content-center m-auto d-flex flex-column" style="width: 90%">
                            <a class="p-4 d-block w-100 h-100 text-decoration-none text-white" href="#team-info">
                                <h2 class="yellow-text">Team</h2>
                                <p class="mb-auto">Get to know all the team members and their background</p>
                            </a>
                        </div>
                    </div>
                </div>

                <div id="whitepaper-info">
                    <white-paper-panel />
                </div>

                <div id="roadmap-info" class="row mt-5">
                    <h1 class="yellow-text shadowed-text my-auto">ROADMAP</h1>
                    <roadmap-carousel />
                </div>

                <div id="team-info" class="h-100">
                    <h1 class="yellow-text shadowed-text">ABOUT THE TEAM</h1>
                    <team-panel />
                </div>
            </div>
        </div>
    </div>
    <!-- TODO: FOOTER? -->
</template>

<script>
import WhitePaperPanel from "../components/WhitePaperPanel.vue"
import RoadmapCarousel from "../components/RoadmapCarousel.vue";
import TeamPanel from '../components/TeamPanel.vue';

export default {
    name: 'Home',
    components: {
        WhitePaperPanel,
        RoadmapCarousel,
        TeamPanel,
    },
    data() {
        return {
            isWindowTop: true,
        }
    },
    mounted() {
        window.addEventListener("scroll", this.onScroll)
    },
    unmounted() {
        window.removeEventListener("scroll", this.onScroll)
    },
    methods: {
        onScroll(event) {
            this.isWindowTop = window.top.scrollY < 100;
        }
    }
}
</script>

<style scoped>
#scroll-down-div{
    width: 100%;
    margin: 0;
    position: absolute;
    bottom: 5px;
    left: 0px;
    padding: 0px;
    padding-bottom: 5px;
}
#scroll-down-img{
    height: 10vh;
}
.magus-img-title {
    width: 50%;
    max-width: 750px;
}
#roadmap-info {
    min-height: 70vh;
}
#team-info {
    height: 80vh;
}
@media screen and (max-width: 991px) {
    .magus-img-title{
        width: 100%;
        height: auto;
        max-width: 60vw;
    }
}
</style>
