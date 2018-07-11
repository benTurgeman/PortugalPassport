<template>
    <div class="contact-detail" :class="{'contact-detail-column' : alignColumn}">
        <div class="contact-detail-title" v-if="alignColumn">
            <span class="contact-detail-title-text">
                שלחו לנו מייל
            </span>
        </div>
        <div class="contact-detail-inputs" :class="{'contact-detail-inputs-column' : alignColumn}">
            <div class="input-container" :class="{'input-container-column' : alignColumn}">
                <span class="align-to-right">טלפון</span>
                <v-text-field v-model="phone"></v-text-field>
            </div>
            <div class="input-container" :class="{'input-container-column' : alignColumn}">
                <span class="align-to-right">דוא"ל</span>
                <v-text-field v-model="email"></v-text-field>
            </div>
            <div class="input-container" :class="{'input-container-column' : alignColumn}">
                <span class="align-to-right">שם מלא</span>
                <v-text-field v-model="name"></v-text-field>
            </div>
        </div>
        <div class="contact-detail-action">
            <v-btn class="blue lighten-2" dark large @click="sendContact()">
                שלח
            </v-btn>
        </div>
    </div>
</template>

<script>
export default {
    props: ['alignColumn'],
    data() {
        return{
            name: null,
            email: null,
            phone: null
        }
    },
    methods:{
        sendContact(){
            let contact = {
                name: this.name,
                email: this.email,
                phone: this.phone
            }
            this.$emit('sendContact', contact)
        }
    }
}
</script>

<style>

.contact-detail-column{
    display: flex;
    flex-flow: column;
    justify-content: flex-end;
}

.contact-detail-title{
    margin: 20px 20px 20px 0;
    font-size: 24px;
    display: flex;
    justify-content: flex-end;
}

.contact-detail-title-text{
    border-bottom: 2px solid rgb(100, 181, 246);
    padding: 2px 0;
    padding-left: 2px;
}

.contact-detail-inputs{
    display: flex;
    flex-flow: row wrap;
    justify-content: space-around;
}

.contact-detail-inputs-column{
    flex-flow:column-reverse;
    align-items: flex-end;
}


.input-container{
    width: 25%;
}
.input-container-column{
    width: 100%;
}

.input-group__input > input{
    direction: rtl !important;
}

.align-to-right{
    float: right;
}
</style>
