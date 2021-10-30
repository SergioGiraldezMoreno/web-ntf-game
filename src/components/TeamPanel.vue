<template>
    <div class="row text-white d-flex align-items-start text-center p-3">
        <!-- TABLEN AND PC SIZE -->
        <div class="d-none d-sm-block p-3 m-auto" style="max-width: 1250px">
            <ul class="nav nav-tabs">
                <li class="nav-item" role="presentation" style="width:33.33%">
                    <img class="m-2" src="../assets/joan-portrait.png" alt="">
                    <button class="nav-link active w-100" id="joan-tab" 
                    data-bs-toggle="tab" data-bs-target="#joan-info" role="tab" aria-selected="true">
                        <p class="fs-4 fw-bold">Joan</p>
                        <p class="fs-5">Blockchain Dev</p>
                    </button>
                </li>
                <li class="nav-item" role="presentation" style="width:33.33%">
                    <img class="m-2" src="../assets/victor-portrait.png" alt="">
                    <button class="nav-link w-100" id="victor-tab" 
                    data-bs-toggle="tab" data-bs-target="#victor-info" role="tab" aria-selected="false">
                        <p class="fs-4 fw-bold">Victor</p>
                        <p class="fs-5">Artist & Designer</p>
                    </button>
                </li>
                <li class="nav-item" role="presentation" style="width:33.33%">
                    <img class="m-2" src="../assets/sergi-portrait.png" alt="">
                    <button class="nav-link w-100 mt-auto" id="sergi-tab" 
                    data-bs-toggle="tab" data-bs-target="#sergi-info" role="tab" aria-selected="false">
                        <p class="fs-4 fw-bold">Sergi</p>
                        <p class="fs-5">FullStack Dev</p>
                    </button>
                </li>
            </ul>
            <div class="tab-content" id="myTabContent">
                <div class="tab-pane fade show active" id="joan-info" role="tabpanel" aria-labelledby="joan-tab">
                    Here will be a brief description of JOAN and his position in the company. Also a bit of his 
                    professional career and studies!
                    <br>
                    <a href="">
                        <img class="media-icon-sized" src="../assets/linkedin.png"/>
                    </a>
                </div>
                <div class="tab-pane fade" id="victor-info" role="tabpanel" aria-labelledby="victor-tab">
                    Here will be a brief description of VICTOR and his position in the company. Also a bit of his 
                    professional career and studies!
                    <br>
                    <a href="">
                        <img class="media-icon-sized" src="../assets/linkedin.png"/>
                    </a>
                </div>
                <div class="tab-pane fade" id="sergi-info" role="tabpanel" aria-labelledby="sergi-tab">
                    Here will be a brief description of SERGI and his position in the company. Also a bit of his 
                    professional career and studies!
                    <br>
                    <a href="">
                        <img class="media-icon-sized" src="../assets/linkedin.png"/>
                    </a>
                </div>
            </div>
        </div>
        <!-- MOBILE SIZE -->
        <div class="d-sm-none w-100">
            <div class="info-box p-1 my-2 mx-auto mobile-team-card">
                <h2>Joan</h2>
                <img class="w-100 rounded" src="../assets/joan-portrait.png" alt="" />
                <div class="py-3 px-2">
                    <h3>Blockchain Dev</h3>
                    <a href="">
                        <img class="media-icon-sized" src="../assets/linkedin.png"/>
                    </a>
                </div>
            </div>
            <div class="info-box p-1 my-2 mx-auto mobile-team-card">
                <h2>Victor</h2>
                <img class="w-100 rounded" src="../assets/victor-portrait.png" alt="" />
                <div class="py-3 px-2">
                    <h3>Artist & Designer</h3>
                    <a href="">
                        <img class="media-icon-sized" src="../assets/linkedin.png"/>
                    </a>
                </div>
            </div>
            <div class="info-box p-1 my-2 mx-auto w-auto mobile-team-card">
                <h2>Sergio</h2>
                <img class="w-100 rounded" src="../assets/sergi-portrait.png" alt="" />
                <div class="py-3 px-2">
                    <h3>FullStack Dev</h3>
                    <a href="">
                        <img class="media-icon-sized" src="../assets/linkedin.png"/>
                    </a>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.mobile-team-card {
    max-width: 300px;
}
.media-icon-sized {
    width: 35px;
}
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
.nav-tabs .nav-link p {
    line-height: 0.8em;
    margin: 8px;
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
