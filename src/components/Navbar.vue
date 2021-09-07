<template>
    <div id="navbar" class="col-auto text-white min-vh-100">
        <div class="w-100 pt-5">
            <router-link to="/" class="d-inline-block w-100 text-center">
                <img class="w-50 mb-4" src="../assets/home-icon.png"/> <!-- HERE GOES THE GAME ICON -->
            </router-link>
        </div>
        <div class="d-flex flex-column align-items-center align-items-sm-start" id="nav">
            <ul class="nav nav-pills flex-column">
                <li class='py-2 mx-1'>
                    <router-link to="/game">
                        <img class="icon-sized" src="../assets/swords-icon.png"/>
                        <span class="d-none d-sm-inline ms-sm-1">GAME</span>
                    </router-link>
                </li>
                <li class='py-2 mx-1'>
                    <router-link to="/market">
                        <img class="icon-sized" src="../assets/swords-icon.png"/>
                        <span class="d-none d-sm-inline ms-sm-1">MARKET</span>
                    </router-link>
                </li>
                <li class='py-2 mx-1'>
                    <router-link to="/about">
                        <img class="icon-sized" src="../assets/swords-icon.png"/>
                        <span class="d-none d-sm-inline ms-sm-1">ABOUT</span>
                    </router-link>
                </li>
                <li class='py-2 mx-1'>
                    <router-link to="/contact">
                        <img class="icon-sized" src="../assets/swords-icon.png"/>
                        <span class="d-none d-sm-inline ms-sm-1">CONTACT</span>
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

.icon-sized {
    width: 40px;
    height: 40px;
}
#navbar {
    box-shadow: 0 0 50px grey;
    position: relative;
    background-image: linear-gradient(to right, rgb(10, 10, 10), rgb(43, 43, 43) 98%);
}
#nav a {
    font-size: 1.3em;
    color: white;
    text-decoration: none;
}
#nav a.router-link-exact-active {
  color: #42b983;
}
</style>