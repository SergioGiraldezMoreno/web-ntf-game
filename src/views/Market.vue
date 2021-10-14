<template>
    <div class="m-0 min-vh-100 bg-dark">
        <div id="filter-div" class="position-fixed text-white text-center p-3">
            <div class="d-flex">
                <!-- TODO: USE THE DATA FIELD TO CONTROL THE FILTER -->
                <div class="border-end pe-1">
                    <button class="filter-button">
                        <img class="filter-panel-icon" src="../assets/blood-icon.png" alt="">
                    </button>
                    <button class="filter-button">
                        <img class="filter-panel-icon" src="../assets/holy-icon.png" alt="">
                    </button>
                    <button class="filter-button">
                        <img class="filter-panel-icon" src="../assets/venom-icon.png" alt="">
                    </button>
                    <button class="filter-button">
                        <img class="filter-panel-icon" src="../assets/shadow-icon.png" alt="">
                    </button>
                </div>
                <div class="border-end px-1">
                    <button class="filter-button">
                        <img class="filter-panel-icon" src="../assets/attack-icon.png" alt="">
                    </button>
                    <button class="filter-button">
                        <img class="filter-panel-icon" src="../assets/defense-icon.png" alt="">
                    </button>
                    <button class="filter-button">
                        <img class="filter-panel-icon" src="../assets/heal-icon.png" alt="">
                    </button>
                </div>
                <div class="ps-1">
                    <button class="filter-button">
                        <img class="filter-panel-icon" src="../assets/copper-icon.png" alt="">
                    </button>
                    <button class="filter-button">
                        <img class="filter-panel-icon" src="../assets/silver-icon.png" alt="">
                    </button>
                    <button class="filter-button">
                        <img class="filter-panel-icon" src="../assets/gold-icon.png" alt="">
                    </button>
                    <button class="filter-button">
                        <img class="filter-panel-icon" src="../assets/ruby-icon.png" alt="">
                    </button>
                    <button class="filter-button">
                        <img class="filter-panel-icon" src="../assets/obsidiana-icon.png" alt="">
                    </button>
                </div>
            </div>
            <!-- TODO: ADD BUTTON TO SHOW AND HIDE THE FILTER PANEL! -->
        </div>
        <div class="container">
            <!-- TODO: FIX THE DISPLAY OF THIS, SOMETHING IS WRONG WITH THE COLS AND THE DISPLAY FLEX -->
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
  data() {
    //   TODO: USE THIS DATA TO CREATE THE FILTER DIV AND ENABLE AND DISABLE THE ICONS!
      filters: [{id: 1, name: "venom", group: "attribute", img: "../assets/venom-icon.png", active: false},
                {id: 2, name: "holy", group: "attribute", img: "../assets/holy-icon.png", active: false},
                {id: 3, name: "shadow", group: "attribute", img: "../assets/shadow-icon.png", active: false},
                {id: 4, name: "blood", group: "attribute", img: "../assets/blood-icon.png", active: false},
                {id: 5, name: "attack", group: "type", img: "../assets/attack-icon.png", active: false},
                {id: 6, name: "defense", group: "type", img: "../assets/defense-icon.png", active: false},
                {id: 7, name: "heal", group: "type", img: "../assets/heal-icon.png", active: false},
                {id: 8, name: "copper", group: "tier", img: "../assets/copper-icon.png", active: false},
                {id: 9, name: "silver", group: "tier", img: "../assets/silver-icon.png", active: false},
                {id: 10, name: "gold", group: "tier", img: "../assets/gold-icon.png", active: false},
                {id: 11, name: "ruby", group: "tier", img: "../assets/ruby-icon.png", active: false},
                {id: 12, name: "obsidiana", group: "tier", img: "../assets/obsidiana-icon.png", active: false}]
  }
}
</script>

<style scoped>
.filter-button {
    width: auto;
    height: auto;
    padding: 0px;
    border: 0px;
    background-color: rgba(0, 0, 0, 0);
}
.filter-subdiv {
    border-right: solid 2px white;
}
.filter-panel-icon{
    margin: 2px;
    width: 40px;
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
        background-color: rgba(0, 0, 0, 0.7);
        left: 50%;
        transform: translateX(-50%);
        border-radius: 0px;
        padding: 0px;
    } 
}
</style>