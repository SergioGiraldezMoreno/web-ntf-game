<template>
    <div id="navbar" class="col-auto position-fixed text-white h-100 p-0 px-sm-3">
        <div class="w-100 pt-2 pt-md-5">
            <router-link to="/" class="d-inline-block w-100 text-center">
                <img id="home-icon" class="mb-md-4" src="../assets/home-icon.png"/> <!-- HERE GOES THE GAME ICON -->
            </router-link>
        </div>
        <div class="d-flex flex-column align-items-center align-items-sm-start" id="nav">
            <ul class="nav nav-pills flex-column">
                <li class='py-md-2 mx-1'>
                    <router-link to="/game">
                        <img class="icon-sized" src="../assets/game-icon.png"/>
                        <span class="d-none d-md-inline ms-md-1">GAME</span>
                    </router-link>
                </li>
                <li class='py-md-2 mx-1'>
                    <router-link to="/market">
                        <img class="icon-sized" src="../assets/market-icon.png"/>
                        <span class="d-none d-md-inline ms-md-1">MARKET</span>
                    </router-link>
                </li>
                <li class='py-md-2 mx-1'>
                    <router-link to="/about">
                        <img class="icon-sized" src="../assets/about-icon.png"/>
                        <span class="d-none d-md-inline ms-md-1">ABOUT</span>
                    </router-link>
                </li>
                <li class='py-md-2 mx-1'>
                    <router-link to="/contact">
                        <img class="icon-sized" src="../assets/contact-icon.png"/>
                        <span class="d-none d-md-inline ms-md-1">CONTACT</span>
                    </router-link>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
  name: "Navbar",
};
</script>

<style scoped>

#home-icon {
    max-width: 90px;
}

#navbar {
    min-width: 60px;
    box-shadow: 0 0 50px grey;
    background-image: linear-gradient(to right, rgb(10, 10, 10, 0.85), rgb(43, 43, 43, 0.85) 98%);
}
#nav li{
    margin: 5px 0;
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
  color: #42b983;
}
</style>