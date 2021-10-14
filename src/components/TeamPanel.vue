<template>
    <div class="main-div row text-white d-flex align-items-start text-center p-3">
        <div class="p-3 m-auto" style="max-width: 1250px">
            <ul class="nav nav-tabs">
                <li class="nav-item" role="presentation" style="width:33.33%">
                    <img class="m-2" src="../assets/joan-portrait.png" alt="">
                    <button class="nav-link active w-100 fw-bold fs-4" id="joan-tab" 
                    data-bs-toggle="tab" data-bs-target="#joan-info" role="tab" aria-selected="true">
                        Joan
                    </button>
                </li>
                <li class="nav-item" role="presentation" style="width:33.33%">
                    <img class="m-2" src="../assets/victor-portrait.png" alt="">
                    <button class="nav-link w-100 fw-bold fs-4" id="victor-tab" 
                    data-bs-toggle="tab" data-bs-target="#victor-info" role="tab" aria-selected="false">
                        Victor
                    </button>
                </li>
                <li class="nav-item" role="presentation" style="width:33.33%">
                    <img class="m-2" src="../assets/sergi-portrait.png" alt="">
                    <button class="nav-link w-100 fw-bold fs-4" id="sergi-tab" 
                    data-bs-toggle="tab" data-bs-target="#sergi-info" role="tab" aria-selected="false">
                        Sergi
                    </button>
                </li>
            </ul>
            <div class="tab-content" id="myTabContent">
                <div class="tab-pane fade show active" id="joan-info" role="tabpanel" aria-labelledby="home-tab">Joan description</div>
                <div class="tab-pane fade" id="victor-info" role="tabpanel" aria-labelledby="profile-tab">Victor description</div>
                <div class="tab-pane fade" id="sergi-info" role="tabpanel" aria-labelledby="contact-tab">Sergi description</div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.tab-content, .nav-tabs .nav-item.show .nav-link, .nav-tabs .nav-link.active{
    color: white;
    background-color: rgb(43, 43, 43, 0.75);
    border: solid 3px rgb(15, 15, 15);
}
.nav-tabs .nav-item.show .nav-link, .nav-tabs .nav-link.active{
    border-bottom: 0;
}
.tab-content{
    padding: 15px;
    border-top: 0;
}
.nav-tabs .nav-link:hover {
    color: white;
}
.nav-tabs .nav-link {
    margin-bottom: 0px;
    color: rgb(179, 179, 179);
    border: solid 3px rgba(61, 61, 61, 0);
    background-color: rgba(61, 61, 61, 0.65);
    border-bottom: 0;
}
.nav-tabs {
    border: 0px;
}
.nav-tabs:hover {
    border: 0px;
}
.nav-tabs .nav-item img {
    width: 65%;
}

@media screen and (max-width: 1199px) {
    .nav-tabs .nav-item img {
        width: 75%;
    }
}
@media screen and (max-width: 767px) {
    .nav-tabs .nav-item img {
        width: 85%;
    }
}
@media screen and (max-width: 575px) {
    .nav-tabs .nav-item img {
        width: 100%;
    }
}

</style>

<script>
export default {
   name: "TeamPanel",
}
</script>
