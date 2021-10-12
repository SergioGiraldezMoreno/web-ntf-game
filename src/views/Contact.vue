<template>
    <div class="main-background m-0 p-3 min-vh-100">
        <div class="main-div row text-white d-flex align-items-start text-center p-3 h-100">
            <div class="info-box p-3 m-auto" style="max-width: 950px">
                <h1 class="shining-text pt-2">Thanks for your interest</h1>
                <h4 class="pb-2">We will be happy to recieve any suggestion, and solve any doubt!</h4>
                <form class="container">
                    <div class="mb-3 row">
                        <input type="email" class="form-control" id="email-input" placeholder="your_email@example.com">
                    </div>
                    <div class="mb-3 row">
                        <textarea class="col-12 form-control" id="email-content-input"
                        rows=6 placeholder="Body of the message"/>
                    </div>
                    <div class="mb-3">
                        <input type="checkbox" class="form-check-input" id="policies-check">
                        <label class="form-check-label" for="policies-check">terms of use and privacy policy</label>
                    </div>
                    <!-- TODO: DISABLE IF TERMS OF USE ARE NOT CHECKED -->
                    <button type="submit" class="px-3 py-1 rounded">Send</button> 
                </form>
            </div>
        </div>
    </div>
</template>

<style scoped>
form{
    max-width: 800px;
    color: rgb(44, 44, 44);
}
form textarea {
    color: rgb(44, 44, 44);
}
form .form-check-label{
    margin-left: 5px;
    color: white;
}
.info-box:hover{
    background-image: linear-gradient(to right, rgba(10, 10, 10, 0.75), rgb(43, 43, 43, 0.75) 98%);    
}
#global-div {
  background-image: url("../assets/magic-background.jpg");
  background-size: cover;
  background-attachment: fixed;
  background-position: center;
}
</style>