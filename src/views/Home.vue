<template>
    <div id="global-div" class="m-0 p-3 min-vh-100">
        <div class="main-div row text-white h-100 d-flex align-items-start text-center">
            <div>
                <div class="d-inline d-lg-none row vh-100 pt-5 d-flex flex-column">
                    <h1 class="main-title shining-text m-0">The Game's Name</h1>
                    <h2 class="m-0 shining-text">some interesting subtitle</h2>
                    <div class="row justify-content-center m-auto">
                        <div class="col-9">
                            <button class="w-100 rounded-3 py-2 fs-3 fw-bold">PLAY NOW</button>
                            <button class="w-100 rounded-3 py-2 fs-3 fw-bold">WHITEPAPER</button>
                        </div>
                    </div>
                </div>
                <div class="d-none d-lg-block row pt-5">
                    <div class="m-auto row vh-100 d-flex flex-column justify-content-center ">
                        <h1 class="main-title shining-text m-0">The Game's Name</h1>
                        <h2 class="m-0 mb-5 shining-text">some interesting subtitle</h2>
                        <div class="row justify-content-center">
                            <button class="me-1 col-3 rounded-3 p-2 fs-3 fw-bold">PLAY NOW</button>
                            <button class="ms-1 col-3 rounded-3 p-2 fs-3 fw-bold">WHITEPAPER</button>
                        </div>
                    </div>
                </div>
                <div class="row equal row-cols-1 row-cols-lg-3 justify-content-center">
                    <div class="col my-4 my-lg-0">
                        <div class="p-4 info-box h-100 justify-content-center m-auto d-flex flex-column" style="width: 90%">
                            <h2 class="yellow-text">Whitepaper</h2>
                            <p class="mb-auto">All you need to know about the project. The technologies, game dynamics, goals...</p>
                        </div>
                    </div>
                    <div class="col my-4 my-lg-0">
                        <div class="p-4 info-box h-100 justify-content-center m-auto d-flex flex-column" style="width: 90%">
                            <h2 class="yellow-text">Roadmap</h2>
                            <p class="mb-auto">All the information about stages, deadlines and the current status of the project</p>
                        </div>
                    </div>
                    <div class="col my-4 my-lg-0">
                        <div class="p-4 info-box h-100 justify-content-center m-auto d-flex flex-column" style="width: 90%">
                            <h2 class="yellow-text">Team</h2>
                            <p class="mb-auto">Get to know all the team members and their background</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>

#global-div {
  background-image: url("../assets/background5.jpg");
  background-size: cover;
  background-attachment: fixed;
  background-position: center;
}

</style>
