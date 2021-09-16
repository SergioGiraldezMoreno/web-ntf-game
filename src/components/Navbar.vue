<template>
    <div class="position-fixed d-flex flex-column align-items-sm-start vh-100 p-0" id="nav">
        <router-link class="d-inline-block text-center p-lg-2" to="/">
            <!-- TODO: ESTE BOTON NO TE LLEVA AL INICIO DE LA PAGINA SI ESTAS YA EN ELLA -->
            <img id="home-icon" src="../assets/magus-icon.png"/>
        </router-link>
        <ul class="p-0 my-auto">
            <li class='m-0 top-right-border-radius'>
                <router-link id='game-link' class="d-inline-block h-100 p-3" to="/game">
                    <img class="icon-sized" src="../assets/game-icon.png"/>
                    <span id='game-link-text' class="align-middle ps-2 fw-bold">PLAY NOW</span>
                </router-link>
            </li>
            <li class='m-0'>
                <router-link id='market-link' class="d-inline-block h-100 p-3" to="/market">
                    <img class="icon-sized" src="../assets/market-icon.png"/>
                    <span id='market-link-text' class="align-middle ps-2 fw-bold">MARKET PLACE</span>
                </router-link>
            </li>
            <li class='m-0 bottom-right-border-radius'>
                <router-link id='contact-link' class="d-inline-block h-100 p-3" to="/contact">
                    <img class="icon-sized" src="../assets/contact-icon.png"/>
                    <span id='contact-link-text' class="align-middle ps-2 fw-bold">CONTACT</span>
                </router-link>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
  name: "Navbar",
};
</script>

<style scoped>
#nav {
    z-index: 1;
}
#game-link-text {
    display: none;
}
#game-link:hover > #game-link-text {
    display: inline;
}
#market-link-text {
    display: none;
}
#market-link:hover > #market-link-text {
    display: inline;
}
#contact-link-text {
    display: none;
}
#contact-link:hover > #contact-link-text {
    display: inline;
}
@media screen and (max-width: 767px) {
    #game-link:hover > #game-link-text {
        display: none;
    }
    #market-link:hover > #market-link-text {
        display: none;
    }
    #contact-link:hover > #contact-link-text {
        display: none;
    }
}
#home-icon {
    max-width: 90px;
}
#nav ul{
    list-style: none;
}
.top-right-border-radius {
    border-top-right-radius: 15px;
}
.bottom-right-border-radius {
    border-bottom-right-radius: 15px;
}
#nav li {
    float: left;
    clear: left;
    background-color: rgba(0, 0, 0, 0.7);
}
#nav a {
    font-size: 1.1em;
    color: white;
    text-decoration: none;
}
#nav a:hover{
    text-shadow: 0 0 10px #000000, 0 0 4px #fbff00;
}
#nav a.router-link-exact-active {
  color: rgb(187, 143, 0);
}
</style>