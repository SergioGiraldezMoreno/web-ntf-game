<template>
    <div class="main-background m-0 p-3 min-vh-100">
        <div class="main-div row text-white d-flex align-items-start text-center p-3 h-100">
            <div class="info-box p-1 p-sm-3 m-auto" style="max-width: 950px">
                <h1 class="shining-text pt-2">Thanks for your interest</h1>
                <h4 class="d-none d-sm-block pb-2">We will be happy to recieve any suggestion, and solve any doubt!</h4>
                <form class="container" @submit.prevent>
                    <div class="mb-3 row">
                        <input type="email" ref="email" class="form-control" id="email-input" placeholder="your_email@example.com" name="email">
                    </div>
                    <div class="mb-3 row">
                        <textarea ref="message" class="col-12 form-control" id="email-content-input"
                        rows=6 placeholder="Body of the message" name="message"/>
                    </div>
                    <div class="mb-3">
                        <input type="checkbox" v-model='policiesCheck' ref='policiesCheck' class="form-check-input" id="policies-check" />
                        <label class="form-check-label" for="policies-check">terms of use and privacy policy</label>
                    </div>
                    <button type="submit" @click="sendEmail()" value="Submit" :disabled="isSubmitDisabled" class="custom-button px-3 py-1 rounded">Send</button> 
                </form>
            </div>
        </div>
        <div v-if="popup_visible" id="message-popup" class="info-box text-center p-3">
            <div class="h-100">
                <h4>{{ popup_text }}</h4>
                <!-- ADD ICON TO MAKE IT CLEARER -->
                <button @click="hidePopupMessage()" id="popup-button" class="custom-button fs-4 m-auto" >OK</button>
            </div>
        </div>
    </div>
</template>
<script>
import axios from 'axios';

export default {
    name: 'Contact',
    data() {
        return {
            policiesCheck: false,
            popup_visible: false,
            popup_text: "",
        }
    },
    methods: {
        sendEmail() {
            let url = "/api/send_email"
            let payload = {
                email: this.$refs.email.value,
                message: this.$refs.message.value
            }
            if (this.$refs.policiesCheck.checked) {
                axios.post(url, payload)
                    .then(res=>{
                        var message = "Thanks a lot for the help, we'll do our best!"
                        this.showPopupMessage(message)
                        console.log('GOOD server response status: ' + res.status);
                        // JSON.stringify(res) to show the values
                    })
                    .catch(err=>{
                        var message = "Something whent wrong... a notification will be sent to the dev team, sorry for the inconveniences"
                        this.showPopupMessage(message)
                        console.log('BAD server response status: ' + err.status);
                        // TODO: Create a log system to store the errors
                    });
            }
        },
        showPopupMessage(message) {
            this.popup_text = message;
            this.popup_visible = true;
        },
        hidePopupMessage() {
            this.popup_visible = false;
        }
    },
    computed: {
        isSubmitDisabled() {
            return !this.policiesCheck
        }
    }
}
</script>

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
#popup-button {
    position: absolute;
    bottom: 10%;
    left: 10%;
    width: 80%;
    border-radius: 5px;
}
#message-popup {
    min-width: 250px;
    min-height: 100px;
    max-width: 380px;
    max-height: 250px;
    border-radius: 10%;
    color: white;
    background-color: rgba(0, 0, 0, 0.85);
    position: fixed;
    margin: auto;
    inset: 0;
}
</style>