<template>
    <div class="icon-cards">
        <div class="cards-container">
            <div class="crad-item">
                <v-card class="elevation-0 transparent">
                    <v-card-text class="text-xs-center">
                        <svg style="width:70px;height:70px" class="icon-svg" viewBox="0 0 24 24">
                            <path fill="#000000" d="M7,5H21V7H7V5M7,13V11H21V13H7M4,4.5A1.5,1.5 0 0,1 5.5,6A1.5,1.5 0 0,1 4,7.5A1.5,1.5 0 0,1 2.5,6A1.5,1.5 0 0,1 4,4.5M4,10.5A1.5,1.5 0 0,1 5.5,12A1.5,1.5 0 0,1 4,13.5A1.5,1.5 0 0,1 2.5,12A1.5,1.5 0 0,1 4,10.5M7,19V17H21V19H7M4,16.5A1.5,1.5 0 0,1 5.5,18A1.5,1.5 0 0,1 4,19.5A1.5,1.5 0 0,1 2.5,18A1.5,1.5 0 0,1 4,16.5Z" />
                        </svg>
                    </v-card-text>
                    <v-card-title primary-title class="layout justify-center">
                        <div class="headline text-xs-center">מספר מסלולים</div>
                    </v-card-title>
                    <v-card-text>
                        <div class="text-lg-center text-md-center text-sm-center text-xs-center">
                            אנו מבצעים את את התהליך במסלולים שיתאימו לכל אחד
                        </div>
                        <div class="text-lg-center text-md-center text-sm-center text-xs-center">
                            מסלול מוזלת, משולב ומסלול עם אחריות מלאה
                        </div>
                    </v-card-text>
                </v-card>
            </div>
            <div class="card-item">
                <v-card class="elevation-0 transparent">
                    <v-card-text class="text-xs-center">
                        <svg style="width:70px;height:70px" viewBox="0 0 24 24">
                            <path fill="#000000" d="M12,11.5A2.5,2.5 0 0,1 9.5,9A2.5,2.5 0 0,1 12,6.5A2.5,2.5 0 0,1 14.5,9A2.5,2.5 0 0,1 12,11.5M12,2A7,7 0 0,0 5,9C5,14.25 12,22 12,22C12,22 19,14.25 19,9A7,7 0 0,0 12,2Z" />
                        </svg>
                    </v-card-text>
                    <v-card-title primary-title class="layout justify-center">
                        <div class="headline text-xs-center">איתך בישראל ובפורטוגל</div>
                    </v-card-title>
                    <v-card-text>
                        <div class="text-lg-center text-md-center text-sm-center text-xs-center">משרדנו עובד בשיתוף פעולה מלא</div>
                        <div class="text-lg-center text-md-center text-sm-center text-xs-center">עם משרד עורכי דין בפורטוגל</div>
                    </v-card-text>
                </v-card>
            </div>
            <div class="card-item">
                <v-card class="elevation-0 transparent">
                    <v-card-text class="text-xs-center">
                        <svg style="width:70px;height:70px" viewBox="0 0 24 24">
                            <path fill="#000000" d="M2.5,19H21.5V21H2.5V19M22.07,9.64C21.86,8.84 21.03,8.36 20.23,8.58L14.92,10L8,3.57L6.09,4.08L10.23,11.25L5.26,12.58L3.29,11.04L1.84,11.43L3.66,14.59L4.43,15.92L6.03,15.5L11.34,14.07L15.69,12.91L21,11.5C21.81,11.26 22.28,10.44 22.07,9.64Z" />
                        </svg>
                    </v-card-text>
                    <v-card-title primary-title class="layout justify-center">
                        <div class="headline text-xs-center">מאות לקוחות מרוצים</div>
                    </v-card-title>
                    <v-card-text>
                        <div class="text-lg-center text-md-center text-sm-center text-xs-center">מאות בקשות שהוגשו דרכנו</div>
                        <div class="text-lg-center text-md-center text-sm-center text-xs-center">כבר אושרו ובדרכם לאזרחות</div>
                    </v-card-text>
                </v-card>
            </div>
        </div>
    </div>
</template>

<script>
export default {};
</script>

<style>

.cards-container{
  display: flex;
  flex-flow: row;
  justify-content: space-around;
  margin: 20px 0;
}

.card-item{
    width: 340px;
}

@media screen and (max-width: 600px){
  .cards-container{
    flex-flow: column;
    align-items: center;
  }
}
</style>
