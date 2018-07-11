<template>
    <div class="heratige-check">
        <div class="heratige-check-title">
            בדקו את זכאותכם בחינם
        </div>
        <div class="heratige-inputs-wraper">
            <div class="parent-input-container">
                <div class="input-container">
                    <span class="align-to-right">שם האב</span>
                    <v-text-field v-model="fatherName"></v-text-field>
                </div>
                <div class="input-container">
                    <span class="align-to-right">ארץ מוצא</span>
                    <v-text-field v-model="fatherCountry"></v-text-field>
                </div>
            </div>
            <div class="parent-input-container">
                <div class="input-container">
                    <span class="align-to-right">שם האם</span>
                    <v-text-field v-model="motherName"></v-text-field>
                </div>
                <div class="input-container">
                    <span class="align-to-right">ארץ מוצא</span>
                    <v-text-field v-model="motherCountry"></v-text-field>
                </div>
            </div>
            <div class="contact-detail-container">
                <contact-detail @sendContact="sendContact"></contact-detail>            
            </div>
        </div>
    </div>
</template>

<script>
import ContactDetail from './ContactDetail'
export default {
    data(){
        return{
            fatherName: null,
            fatherCountry: null,
            motherName: null,
            motherCountry: null
        }
    },
    methods:{
        sendContact(contact){
            contact.heratige = {
                fatherName: this.fatherName,
                fatherCountry: this.fatherCountry,
                motherName: this.motherName,
                motherCountry: this.motherCountry
            }
            this.$emit('sendContact', contact)
        }
    },
    components:{
        ContactDetail
    }
}
</script>


<style scoped>

.heratige-check-title{
    text-align: center;
    font-size: 24px;
    margin: 0 0 35px 0;
}

.heratige-inputs-wraper{
    display: flex;
    flex-flow: column;
    justify-content: flex-end
}

.parent-input-container{
    display: flex;
    flex-flow: row-reverse;
    /* justify-content: flex-end;  */
    justify-content: space-around;
}

.input-container{
    width: 40%
}


</style>
