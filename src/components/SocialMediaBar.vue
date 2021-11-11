<template>
    <div class="w-auto position-fixed d-flex flex-column align-items-sm-end vh-100 p-0" id="nav">
         <ul class="pb-0 px-0 my-auto">
            <li class='m-0 top-left-border-radius'>
                <a id='twitter-link' class="d-inline-block h-100 p-2">
                    <img class="media-icon-sized" src="../assets/twitter.png"/>
                </a>
            </li>
            <li class='m-0'>
                <a id='instagram-link' class="d-inline-block h-100 p-2">
                    <img class="media-icon-sized" src="../assets/instagram.jpg"/>
                </a>
            </li>
            <li class='m-0 bottom-left-border-radius'>
                <a id='linkedin-link' class="d-inline-block h-100 p-2">
                    <img class="media-icon-sized" src="../assets/linkedin.png"/>
                </a>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
  name: "SocialMediaBar",
};
</script>

<style scoped>
#nav {
    right: 0;
}
#nav ul{
    padding-top: 90px;
    list-style: none;
}
.media-icon-sized {
    width: 35px;
}
.top-left-border-radius {
    border-top-left-radius: 15px;
}
.bottom-left-border-radius {
    border-bottom-left-radius: 15px;
}
#nav li {
    float: right;
    clear: right;
    background-color: rgba(0, 0, 0, 0.7);
}
#twitter-link {
    background-color: rgb(29, 161, 242);
}
#instagram-link {
    background-color: rgb(193, 53, 132);
}
#linkedin-link {
    background-color: rgb(14, 118, 168);
}
@media screen and (max-width: 767px){
    #nav ul{
        padding-top: 50px;
    }
}
</style>