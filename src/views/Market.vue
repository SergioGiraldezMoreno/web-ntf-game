<template>
    <div class="m-0 min-vh-100 bg-dark">
        <div id="filter-div" class="position-fixed text-white text-center p-3">Here will go the filtering options</div>
        <div class="container">
            <div id="card-container" class="row d-flex row-cols-1 gy-2">
            <!-- <div class="row row-cols-1 row-cols-sm-1 row-cols-md-1 row-cols-lg-2 row-cols-xl-3 gy-2" style="margin-top: 100px;"> -->
                <!-- <MarketPlaceCard class="col mx-auto"/> -->
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