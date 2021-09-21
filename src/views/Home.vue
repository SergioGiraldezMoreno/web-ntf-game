<template>
    <!-- <div id="global-div" class="m-0 p-3 min-vh-100"> -->
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
            
                <div class="row equal row-cols-1 row-cols-lg-3 justify-content-center">
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
                            <a class="p-4 d-block w-100 h-100 text-decoration-none text-white" href="">
                                <h2 class="yellow-text">Roadmap</h2>
                                <p class="mb-auto">All the information about stages, deadlines and the current status of the project</p>
                            </a>
                        </div>
                    </div>
                    <div class="col my-4 my-lg-0">
                        <div class="info-box h-100 justify-content-center m-auto d-flex flex-column" style="width: 90%">
                            <a class="p-4 d-block w-100 h-100 text-decoration-none text-white" href="">
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

                <!-- SVG roadmap like an old map -->
                <!-- <div id="roadmap-info" class="row p-3">
                    <div class="row">
                        <div class="bg-dark col-4">STAGE 1</div>
                        <div class="col-6" style="height: 150px; overflow: hidden;" >
                            <svg viewBox="0 0 500 150" preserveAspectRatio="none" style="height: 100%; width: 100%;">
                                <path id="svg-path" stroke-dasharray="10,10" d="M-52.20,55.75 C149.99,150.00 556.15,-114.95 505.92,289.63"></path>
                            </svg>
                        </div>
                    </div>
                    <div class="row justify-content-end">
                        <div class="col-6" style="height: 150px; overflow: hidden;" >
                            <svg viewBox="0 0 500 150" preserveAspectRatio="none" style="height: 100%; width: 100%;">
                                <path id="svg-path" stroke-dasharray="10,10" d="M-4.79,199.83 C-16.08,-53.78 455.70,91.28 526.80,85.36"></path>
                            </svg>
                        </div>
                        <div class="bg-dark col-4">STAGE 2</div>
                    </div>
                    <div class="row">
                        <div class="bg-dark col-4">STAGE 3</div>
                    </div>
                    <div class="row"></div>
                    <div class="row"></div>
                </div> -->

                <!-- TEST -->
                <div class="container">
                    <div class="row">
                        <div class="container-fluid">
                            <div id="carousel-example" class="carousel slide" data-interval="false">
                                <div class="carousel-inner row w-100 mx-auto" role="listbox">
                                    <div class="carousel-item carousel-item-mine col-12 col-sm-6 col-md-4 col-lg-3 active">
                                        <img src="../assets/fire-skill.png" class="img-fluid mx-auto d-block" alt="img1">
                                    </div>
                                    <div class="carousel-item carousel-item-mine col-12 col-sm-6 col-md-4 col-lg-3">
                                        <img src="../assets/old_paper_texture2.png" class="img-fluid mx-auto d-block" alt="img2">
                                    </div>
                                    <div class="carousel-item carousel-item-mine col-12 col-sm-6 col-md-4 col-lg-3">
                                        <img src="../assets/fire-skill.png" class="img-fluid mx-auto d-block" alt="img3">
                                    </div>
                                    <div class="carousel-item carousel-item-mine col-12 col-sm-6 col-md-4 col-lg-3">
                                        <img src="../assets/old_paper_texture2.png" class="img-fluid mx-auto d-block" alt="img4">
                                    </div>
                                    <div class="carousel-item carousel-item-mine col-12 col-sm-6 col-md-4 col-lg-3">
                                        <img src="../assets/fire-skill.png" class="img-fluid mx-auto d-block" alt="img5">
                                    </div>
                                    <div class="carousel-item carousel-item-mine col-12 col-sm-6 col-md-4 col-lg-3">
                                        <img src="../assets/old_paper_texture2.png" class="img-fluid mx-auto d-block" alt="img6">
                                    </div>
                                    <div class="carousel-item carousel-item-mine col-12 col-sm-6 col-md-4 col-lg-3">
                                        <img src="../assets/fire-skill.png" class="img-fluid mx-auto d-block" alt="img7">
                                    </div>
                                    <div class="carousel-item carousel-item-mine col-12 col-sm-6 col-md-4 col-lg-3">
                                        <img src="../assets/old_paper_texture2.png" class="img-fluid mx-auto d-block" alt="img8">
                                    </div>
                                </div>
                                <a class="carousel-control-prev" role="button" data-bs-target="#carousel-example" data-bs-slide="prev">
                                    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                                    <span class="sr-only">Previous</span>
                                </a>
                                <a class="carousel-control-next" role="button" data-bs-target="#carousel-example" data-bs-slide="next">
                                    <span class="sr-only">Next</span>
                                    <span class="carousel-control-next-icon" aria-hidden="true"></span>
                                </a>
                            </div>
                        </div>
                    </div>
                </div>
                <!-- END TEST -->
<!-- 
                <div id="roadmap-info" class="row">
                    <h1 class="yellow-text shadowed-text mb-5">ROADMAP</h1>
                    <div class="container">
                        <div class="row equal row-cols-1 row-cols-lg-4 justify-content-center">
                            <div class="col my-4 my-lg-0">
                                <div class="info-box h-100 justify-content-center m-auto d-flex flex-column p-2" style="width: 90%">
                                    <h2 class="yellow-text">Stage 1</h2>
                                    <h5 class="yellow-text fw-bold">2021 Q3</h5>
                                    <p class="mb-auto">
                                        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
                                        incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud 
                                        exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute 
                                        irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                                    </p>
                                </div>
                            </div>
                            <div class="col my-4 my-lg-0">
                                <div class="info-box h-100 justify-content-center m-auto d-flex flex-column p-2" style="width: 90%">
                                    <h2 class="yellow-text">Stage 1</h2>
                                    <h5 class="yellow-text fw-bold">2021 Q3</h5>
                                    <p class="mb-auto">
                                        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
                                        incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud 
                                        exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute 
                                        irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                                    </p>
                                </div>
                            </div>
                            <div class="col my-4 my-lg-0">
                                <div class="info-box h-100 justify-content-center m-auto d-flex flex-column p-2" style="width: 90%">
                                    <h2 class="yellow-text">Stage 1</h2>
                                    <h5 class="yellow-text fw-bold">2021 Q3</h5>
                                    <p class="mb-auto">
                                        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
                                        incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud 
                                        exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute 
                                        irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                                    </p>
                                </div>
                            </div>
                            <div class="col my-4 my-lg-0">
                                <div class="info-box h-100 justify-content-center m-auto d-flex flex-column p-2" style="width: 90%">
                                    <h2 class="yellow-text">Stage 1</h2>
                                    <h5 class="yellow-text fw-bold">2021 Q3</h5>
                                    <p class="mb-auto">
                                        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
                                        incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud 
                                        exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute 
                                        irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                                    </p>
                                </div>
                            </div>
                            <div class="col my-4 my-lg-0">
                                <div class="info-box h-100 justify-content-center m-auto d-flex flex-column p-2" style="width: 90%">
                                    <h2 class="yellow-text">Stage 1</h2>
                                    <h5 class="yellow-text fw-bold">2021 Q3</h5>
                                    <p class="mb-auto">
                                        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
                                        incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud 
                                        exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute 
                                        irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                                    </p>
                                </div>
                            </div>
                            <div class="col my-4 my-lg-0">
                                <div class="info-box h-100 justify-content-center m-auto d-flex flex-column p-2" style="width: 90%">
                                    <h2 class="yellow-text">Stage 1</h2>
                                    <h5 class="yellow-text fw-bold">2021 Q3</h5>
                                    <p class="mb-auto">
                                        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
                                        incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud 
                                        exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute 
                                        irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                                    </p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div> -->
                
            </div>
        </div>
    </div>
</template>


<style scoped>

/* TEST */
.carousel-item-mine img{
    width: 400px;
    height: 400px;
}
.carousel-inner .carousel-item-right.active,
.carousel-inner .carousel-item-next {
  transform: translateX(33.33%);
}

.carousel-inner .carousel-item-left.active, 
.carousel-inner .carousel-item-prev {
  transform: translateX(-33.33%)
}

.carousel-inner .carousel-item-right,
.carousel-inner .carousel-item-left{ 
  transform: translateX(0);
}
/* END TEST */
/* #svg-path{
    stroke: rgb(124, 0, 0);
    stroke-width: 6px;
    fill: none;
}
#roadmap-info{
    background-color: rgba(0, 0, 0, 0); */
    /* background-image: url("../assets/old_paper_texture.jpg"); */
    /* background-image: url("../assets/old_paper_texture2.png");
    background-size: cover; 
}*/
#whitepaper-info{
    color: rgb(61, 32, 12);
    background-image: url("../assets/papiro.png");
    background-size: 100% 100%;
}
</style>
