<template>
    <div class="position-fixed d-flex flex-column align-items-sm-end vh-100 p-0" id="nav">
         <ul class="pb-0 px-0 my-auto" style="padding-top: 90px;">
            <li class='m-0 top-left-border-radius'>
                <a id='twitter-link' class="d-inline-block h-100 p-3">
                    <!-- TODO: UPDATE THE ICON! -->
                    <img class="icon-sized" src="../assets/game-icon.png"/>
                </a>
            </li>
            <li class='m-0'>
                <a id='instagram-link' class="d-inline-block h-100 p-3">
                    <!-- TODO: UPDATE THE ICON! -->
                    <img class="icon-sized" src="../assets/market-icon.png"/>
                </a>
            </li>
            <li class='m-0 bottom-left-border-radius'>
                <a id='linkedin-link' class="d-inline-block h-100 p-3">
                    <!-- TODO: UPDATE THE ICON! -->
                    <img class="icon-sized" src="../assets/contact-icon.png"/>
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

#nav ul{
    list-style: none;
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

</style>