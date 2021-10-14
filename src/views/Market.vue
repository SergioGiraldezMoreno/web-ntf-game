<template>
    <div class="m-0 min-vh-100 bg-dark">
        <div id="filter-div" class="position-fixed text-white text-center p-3">
            <p class="p-0 m-0">filter</p>
            <form class="d-flex" action="">
                <div class="p1">
                    <!-- skill attribute filter -->
                    <div class="ms-1 d-flex" style="border-bottom: 1px solid white;">
                        <div class="filter-subdiv-check m-auto">
                            <input id="-checkbox" type="checkbox">
                            <img class="filter-panel-icon" src="../assets/attack-icon.png" alt="">
                        </div>
                        <div class="filter-subdiv-check m-auto">
                            <input id="defense-checkbox" type="checkbox">
                            <img class="filter-panel-icon" src="../assets/defense-icon.png" alt="">
                        </div>
                        <div class="filter-subdiv-check m-auto">
                            <input id="heal-checkbox" type="checkbox">
                            <img class="filter-panel-icon" src="../assets/heal-icon.png" alt="">
                        </div>
                    </div>
                    <!-- skill type filter -->
                    <div class="ms-1 d-flex">
                        <div class="filter-subdiv-check">
                            <input id="attack-checkbox" type="checkbox">
                            <img class="filter-panel-icon" src="../assets/icon-blood.png" alt="">
                        </div>
                        <div class="filter-subdiv-check">
                            <input id="defense-checkbox" type="checkbox">
                            <img class="filter-panel-icon" src="../assets/defense-icon.png" alt="">
                        </div>
                        <div class="filter-subdiv-check">
                            <input id="heal-checkbox" type="checkbox">
                            <img class="filter-panel-icon" src="../assets/heal-icon.png" alt="">
                        </div>
                    </div>
                </div>
            </form>
            <!-- <div class="fs-6">Iconos diseñados por <a href="https://www.flaticon.es/autores/good-ware" title="Good Ware">Good Ware</a> from <a href="https://www.flaticon.es/" title="Flaticon">www.flaticon.es</a></div> -->
        </div>
        <div class="container">
            <div id="card-container" class="row d-flex row-cols-1 gy-2">
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
                <MarketPlaceCard class="col mx-auto"/>
            </div>
        </div>
    </div>
</template>

<script>
import MarketPlaceCard from "../components/MarketPlaceCard.vue";

export default {
  name: 'Market',
  components: {
    MarketPlaceCard,
  },
}
</script>

<style scoped>
/* .filter-subdiv{
    border-right: 1px solid white;
} */
.filter-subdiv-check{
    display: flex;
    justify-content: center;
    align-items: center;
}
.filter-panel-icon{
    /* margin: auto;
    display: block; */
    margin: 2px;
    width: 20px;
}
#card-container {
    margin-left: 25px;
    margin-right: 15px;
    margin-top: 100px;
}
#filter-div{
    background-color: rgba(0, 0, 0, 0.7);
    left: 50%;
    transform: translateX(-50%);
    border-radius: 0 0 20px 20px;
    padding: 0px;
    z-index: 1;
}
@media screen and (max-width: 767px) {
    #card-container {
        margin-left: 45px;
        margin-right: 30px;
    }
    #filter-div{    
        /* width: 50%; */
        background-color: rgba(0, 0, 0, 0.7);
        left: 50%;
        transform: translateX(-50%);
        border-radius: 0px;
        padding: 0px;
    } 
}
</style>