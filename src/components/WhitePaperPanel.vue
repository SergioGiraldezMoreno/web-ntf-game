<template>
    <!-- TODO: REPLACE THE SCROLL IMAGE WITH 3 IMGS OF EACH PART SO THE HEAD AND FOOT ARE THE ROLLS AND THE BODY IS THE PAPER -->
    <div class="whitepaper-info-container container p-5 vh-100 d-none d-md-block ">
        <div class="whitepaper-info-subcontainer mx-auto w-75 overflow-auto">
            <h1>WHITEPAPER</h1>
            <!-- TODO: CONTENT -->
            <p class="fs-4 fw-bold">Here will go all the whitepaper info, maybe with some info in sliders, 
                each slider talking about a particular topic. (la animacion entre las paginas podria ser un
                fundido y que aparezca la nueva info.)
            </p>
            <p class="fs-4 fw-bold">
                Deberia haber un boton para moverte entre sliders (alguna forma de indice tambien para navegar mas rapido)
                y un boton (link) al whitepaper completo o para descargarlo
            </p>
            <p class="fs-4 fw-bold">
                1 Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            </p>
            <p class="fs-4 fw-bold">
                2 Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            </p>
            <p class="fs-4 fw-bold">
                3 Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            </p>
            <p class="fs-4 fw-bold">
                4 Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            </p>
            <p class="fs-4 fw-bold">
                5 Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            </p>
            <p class="fs-4 fw-bold">
                6 Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            </p>
        </div>
    </div>
    <div class="d-md-none whitepaper-info-container p-4">
        <div class="whitepaper-info-subcontainer d-flex flex-column">
            <h1>WHITEPAPER</h1>
            <!-- TODO: CONTENT -->
            <p>Here should be just a short message telling the user to read or download the content.</p>
            <!-- TODO: LINK -->
            <button class="my-1 mx-auto">Read more</button>
            <button class="mx-auto">Download PDF</button>
        </div>
    </div>
</template>

<script>
export default {
   name: "WhitePaperPanel",
}
</script>

<style scoped>
.whitepaper-info-container {
    color: rgb(61, 32, 12);
    background-image: url("../assets/papiro_light.png");
    background-size: 100% 100%;
    max-width: 110vh;
}
.whitepaper-info-container button {
    background-color: rgb(61, 32, 12);
    background-image: linear-gradient(to right, rgb(61, 32, 12), rgb(88, 54, 31) 90%);
    border-radius: 10px;
    border: 0px;
    padding: 5px 10px;
    color: rgb(255, 209, 23);
    width: 100%;
    max-width: 45vw;
}
.whitepaper-info-container ::-webkit-scrollbar-track {
    display: none;
}
.whitepaper-info-container ::-webkit-scrollbar-button:single-button {
    height: 20px;
    width: 20px;
}
.whitepaper-info-container ::-webkit-scrollbar-button:single-button:vertical:decrement {
    background-image: url("../assets/arrow-up.png");
    background-size: 100% 100%;
}
.whitepaper-info-container ::-webkit-scrollbar-button:single-button:vertical:increment {
    background-image: url("../assets/arrow-down.png");
    background-size: 100% 100%;
}
.whitepaper-info-container ::-webkit-scrollbar {
	width: 20px;
	background-color: #ffffff00;
}
.whitepaper-info-container ::-webkit-scrollbar-thumb {
    display: none;
}
.whitepaper-info-subcontainer{
    margin-top: 10vh;
    height: 80%;
    margin-bottom: 10vh;
}
@media screen and (max-width: 767px) {
    .whitepaper-info-container {
        height: auto;
    }
    .whitepaper-info-subcontainer{
        margin-top: 7vh;
        margin-bottom: 6vh;
        height: auto;
    }
}
</style>
