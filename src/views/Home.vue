<template>
    <div id="global-div" class="m-0 p-3 min-vh-100">
        <div class="main-div row text-white h-100 d-flex align-items-start text-center">
            <div>
                <h1 class="main-title shining-text">HOME</h1>
                <div class="row d-none d-lg-inline" ><div style="height: 50vh"></div></div>
                <div class="row equal row-cols-1 row-cols-lg-3 justify-content-center">
                    <div class="col my-4 my-lg-0">
                        <div class="p-4 info-box h-100 justify-content-center m-auto d-flex flex-column" style="width: 90%">
                            <h2 class="yellow-text">Whitepaper</h2>
                            <p>All you need to know about the project. The technologies, game dynamics, goals...</p>
                            <button class="mt-auto">Read more</button>
                        </div>
                    </div>
                    <div class="col my-4 my-lg-0">
                        <div class="p-4 info-box h-100 justify-content-center m-auto d-flex flex-column" style="width: 90%">
                            <h2 class="yellow-text">Roadmap</h2>
                            <p>All the information about stages, deadlines and the current status of the project</p>
                            <button class="mt-auto">Read more</button>
                        </div>
                    </div>
                    <div class="col my-4 my-lg-0">
                        <div class="p-4 info-box h-100 justify-content-center m-auto d-flex flex-column" style="width: 90%">
                            <h2 class="yellow-text">Team</h2>
                            <p>Get to know all the team members and their background</p>
                            <button class="mt-auto">Read more</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>

#global-div {
  /* background-image: url("../assets/mage-background.jpg"); */
  /* background-image: url("../assets/spellbook-2-background.jpg"); */
  /* background-image: url("../assets/spellbook-background.jpg"); */
  background-image: url("../assets/magic-background.jpg");
  background-size: cover;
  background-attachment: fixed;
  background-position: center;
}

</style>
