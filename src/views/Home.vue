<template>
    <div class="main-background m-0 p-3 min-vh-100">
        <div class="main-div row text-white h-100 d-flex align-items-start text-center">
            <div>
                <div class="d-inline d-lg-none row vh-100 pt-5 d-flex flex-column">
                    <img src="../assets/magus.png" alt="">
                    <div class="row justify-content-center m-auto">
                        <div class="col-9">
                            <button class="mb-1 w-100 rounded-3 py-2 fs-3 fw-bold">PLAY NOW</button>
                            <button class="mt-1 w-100 rounded-3 py-2 fs-3 fw-bold">GET STARTED</button>
                        </div>
                    </div>
                </div>
                <div class="d-none d-lg-block row pt-5">
                    <div class="m-auto row vh-100 d-flex flex-column justify-content-center">
                        <img class="mx-auto magus-img-title" src="../assets/magus.png" alt="">
                        <div class="row justify-content-center">
                            <button class="me-1 col-3 rounded-3 p-2 fs-3 fw-bold">PLAY NOW</button>
                            <button class="ms-1 col-3 rounded-3 p-2 fs-3 fw-bold">GET STARTED</button>
                        </div>
                    </div>
                </div>

                <div class="row equal row-cols-1 row-cols-lg-3 justify-content-center mb-5">
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

                <div id="whitepaper-info" class="container p-5 vh-100">
                    <div class="m-auto w-75 mt-5 pt-5">
                        <h1>WHITEPAPER</h1>
                        <p class="fs-4 fw-bold">Here will go all the whitepaper info, maybe with some info in sliders, 
                            each slider talking about a particular topic. (la animacion entre las paginas podria ser un
                            fundido y que aparezca la nueva info.)
                        </p>
                        <p class="fs-4 fw-bold">
                            Deberia haber un boton para moverte entre sliders (alguna forma de indice tambien para navegar mas rapido)
                            y un boton (link) al whitepaper completo o para descargarlo
                        </p>
                    </div>
                </div>

                <div id="roadmap-info" class="row mt-5">
                    <h1 class="yellow-text shadowed-text">ROADMAP</h1>
                    <roadmap-carousel class="mt-3"/>
                </div>

                <div id="team-info">
                    <h1 class="yellow-text shadowed-text">INFO ABOUT THE TEAM</h1>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import RoadmapCarousel from "../components/RoadmapCarousel.vue";

export default {
  name: 'Home',
  components: {
    RoadmapCarousel,
  },
}
</script>

<style scoped>

#whitepaper-info {
    color: rgb(61, 32, 12);
    background-image: url("../assets/papiro.png");
    background-size: 100% 100%;
}

#roadmap-info {
    min-height: 70vh;
}

#team-info {
    height: 80vh;
}

</style>
