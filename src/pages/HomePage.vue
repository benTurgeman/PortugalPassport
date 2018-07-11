<template>
  <div class="hello">
    <v-toolbar class="white">
      <v-toolbar-title></v-toolbar-title>
    </v-toolbar>
    <div class="logo-container">
    <img src="../assets/portugal-flag-3d-round-icon-256.png" class="flag-image">
    <div class="page-header-title">Euro Passporte</div>
    </div>

        <v-parallax :src="require('@/assets/porto-1972486_1920.jpg')" height="450">
          <v-layout column align-center justify-center class="white--text">
          </v-layout>
        </v-parallax>

      <div class="main-content-container">
        <div class="main-content-header">
          <div class="text-xs-center">
            <h2 class="headline">אזרחות פורטוגלית במסלול מהיר</h2>
            <span class="subheading">
              <div>אצלנו מבצעים את כל התהליך מתחילתו ועד סופו במספר מסלולים</div>
              <div>ליווי מתחילת התהליך ועד האישור לקבלת אזרחות</div>
            </span>
          </div>
        </div>

        <div class="icon-cards-container">
          <icon-cards></icon-cards>
        </div>
      </div>

      <div class="heratige-check-container">
          <heratige-check @sendContact="sendContact"></heratige-check>
      </div>

      <section>
        <v-parallax :src="require('@/assets/sea-city-landscape-sky.jpg')" height="300">
        </v-parallax>
      </section>

      <section>
        <div class="footer-container">
          <contact-detail :alignColumn="true" @sendContact="sendContact"></contact-detail>
          <contact-us></contact-us>
          <about-us></about-us>
        </div>
      </section>

      <v-dialog v-model="mailSendDialog" max-width="500px">
        <v-card>
          <v-card-title>
            <div class="text-align-right">ההודעה נשלחה</div>
          </v-card-title>
          <v-card-text>
            <div class="text-align-right">ניצור איתך קשר בהקדם</div>
          </v-card-text>
          <v-card-actions>
            <v-btn color="primary" flat @click.stop="mailSendDialog=false"> סגור</v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
      <v-dialog v-model="mailErrorDialog" max-width="500px">
        <v-card>
          <v-card-title>
            <div class="text-align-right">השליחה נכשלה</div>
          </v-card-title>
          <v-card-text>
            <div class="text-align-right">אנא וודא שכל השדות מולאו</div>
          </v-card-text>
          <v-card-actions>
            <v-btn color="primary" flat @click.stop="mailErrorDialog=false">סגור</v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
  </div>
</template>

<script>
import IconCards from '../components/IconCards'
import HeratigeCheck from '../components/HeratigeCheck'
import ContactDetail from '../components/ContactDetail'
import ContactUs from '../components/ContactUs'
import AboutUs from '../components/AboutUs'
const axios = require('axios');
const server = 'https://us-central1-euro-passport-5cbfa.cloudfunctions.net/api'

export default {
  data() {
    return {
        mailSendDialog: false,
        mailErrorDialog: false
    }
  },
  methods:{
    sendContact(contactDetails){
      if(!!contactDetails.heratige) this.sendHeratigeMail(contactDetails)
      else this.sendNoneHeratigeMail(contactDetails)
      return
    },
    sendNoneHeratigeMail(contactDetails){
      if(!this.checkValidFields(contactDetails)) this.mailErrorDialog = true
      else {
        this.sendEmail('sendMail',contactDetails)
        this.mailSendDialog = true
      } 
      return
    },
    sendHeratigeMail(contactDetails){
      if(!this.checkValidFields(contactDetails)) this.mailErrorDialog = true
      else {
        this.sendEmail('sendFullMail',contactDetails)
        this.mailSendDialog = true
      } 
      return
    },
    checkValidFields(contactDetails){
      if(!contactDetails.name) return false
      if(!this.validateEmail(contactDetails.email)) return false
      return true
    },
    validateEmail(email) {
      let re = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
      let res = re.test(String(email).toLowerCase());
      return res
    },
    sendEmail(type, contactDetails){
      axios.post(`${server}/${type}`,{
            ...contactDetails
        })
        .then(_ => {
            console.log(_)
        })
        .catch(_ => {
            console.log(_)
        })
    }
  },
  components:{
    IconCards,
    HeratigeCheck,
    ContactDetail,
    ContactUs,
    AboutUs
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>


.logo-container{
  position: absolute;
  top: 0;
  left: 0;
  z-index: 2;
  display: flex;
  flex-flow: row nowrap;
  align-items: flex-start
}

.flag-image{
  height: 120px;
}

.page-header-title{
  margin: 12px 0 0 10px;
  font-size: 29px;
}

@media screen and (max-width: 380px){
  .page-header-title{
    font-size: 23px
  }
}

.main-content-container{
  margin: 0 7%;
}

.main-content-header{
  margin: 20px 0;
}

.heratige-check-container{
  margin: 50px 7% 30px 7%;
}

.footer-container{
  display: flex;
  flex-flow: row;
  justify-content: space-around;
  margin: 0 7%;
}

.input-group{
  padding: 0 !important;
}
.text-align-right{
  direction: rtl;
  width: 100%;
}
</style>
