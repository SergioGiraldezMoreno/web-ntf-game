<template>
    <div class="market-card card p-1 text-white">
        <img :src="require('@/'+skill.img)" class="market-card-img" alt="...">
        <div class="card-body d-flex flex-column text-center">
            <p class="market-card-title fs-4 fw-bold">{{skill.name}}</p>
            <p class="market-card-text fs-6">
                {{skill.description}}
            </p>
            <a href="#" class="btn fw-bold card-button mt-auto">Buy (999$)</a>
        </div>
    </div>
</template>

<script>
export default {
    name: "MarketPlaceCard",
    props: {
        skill: Object
    }
};
</script>

<style scoped>
.market-card {
    max-width: 15rem;
    box-shadow: 0 0 10px rgb(105, 105, 105);
    border-radius: 5px;
    background-image: linear-gradient(to right, rgb(10, 10, 10), rgb(37, 37, 37) 95%);
}
.market-card-img {
    border-radius: 5px;
    width: 100%;
    height: auto;
    background-color: rgba(46, 46, 46, 0); /* TODO: change to this when real img are loaded! */
    /* background-image: linear-gradient(to right, rgb(46, 46, 46), rgb(70, 65, 51) 95%); */
}
.market-card-title {
    color: rgb(223, 182, 0);
    text-shadow: 0 0 15px #000000, 0 0 2px #fbff00;
}
.card-button {
    color: rgb(10, 10, 10);
    background-image: linear-gradient(to right, rgb(121, 92, 0), rgb(196, 150, 0) 98%);
}

</style>