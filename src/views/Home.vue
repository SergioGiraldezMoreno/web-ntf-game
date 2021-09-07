<template>
    <div id="start-div" class="m-0 p-3 min-vh-100">
        <div class="main-div row text-white min-vh-100 d-flex align-items-start">
            <div>
                <h1 class="main-title text-start">HOME</h1>
                <h2>Subtitle madaf***a</h2>
                <p>Yeah man, that's it!</p>
            </div>
        </div>
        <div class="main-div row text-white justify-content-center">
            <div class=" col-10 bg-dark rounded p-2">
                <h2>Subtitle again</h2>
                <p>Okey so here is some more text</p>
            </div>
        </div>
    </div>
</template>

<style scoped>

.main-div {
    /* make it responsive for small screens become 72 px */
    margin-left: 160px;
}

#start-div {
  background-image: url("../assets/magic-background.jpg");
  background-size: cover;
  background-attachment: fixed;
}

.main-title{
  text-shadow: 0 0 10px #000000, 0 0 5px #fbff00;
  font-size: 4rem;
  font-weight: 730;
}
</style>
