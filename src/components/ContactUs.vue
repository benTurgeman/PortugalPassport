<template>
    <div class="contact">
        <div class="contact-title">
            <span class="contact-title-text">צור קשר</span>
        </div>
        <div class="contact-content">
            <div class="contact-item">
                <div class="contact-item-content">
                    0525560570 ארז
                </div>
                <div class="contact-item-icon">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
                        <path d="M0 0h24v24H0z" fill="none"/>
                        <path fill="rgb(100, 181, 246)" d="M6.62 10.79c1.44 2.83 3.76 5.14 6.59 6.59l2.2-2.2c.27-.27.67-.36 1.02-.24 1.12.37 2.33.57 3.57.57.55 0 1 .45 1 1V20c0 .55-.45 1-1 1-9.39 0-17-7.61-17-17 0-.55.45-1 1-1h3.5c.55 0 1 .45 1 1 0 1.25.2 2.45.57 3.57.11.35.03.74-.25 1.02l-2.2 2.2z"/>
                    </svg>
                </div>
            </div>
            <div class="contact-item">
                    <div class="contact-item-content">
                        0509555216 אלירן
                    </div>
                <div class="contact-item-icon">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
                        <path d="M0 0h24v24H0z" fill="none"/>
                        <path fill="rgb(100, 181, 246)" d="M6.62 10.79c1.44 2.83 3.76 5.14 6.59 6.59l2.2-2.2c.27-.27.67-.36 1.02-.24 1.12.37 2.33.57 3.57.57.55 0 1 .45 1 1V20c0 .55-.45 1-1 1-9.39 0-17-7.61-17-17 0-.55.45-1 1-1h3.5c.55 0 1 .45 1 1 0 1.25.2 2.45.57 3.57.11.35.03.74-.25 1.02l-2.2 2.2z"/>
                    </svg>
                </div>
            </div>
            <div class="contact-item">
                <div class="contact-item-content">
                    europassporte@gmail.com
                </div>
                <div class="contact-item-icon">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
                        <path fill="rgb(100, 181, 246)" d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/>
                        <path d="M0 0h24v24H0z" fill="none"/>
                    </svg>
                </div>
            </div>
        </div>

    </div>
</template>

<script>
export default {

}
</script>

<style>
.contant{
    direction: rtl;
    display: flex;
    flex-flow: column;
}

.contact-title{
    margin: 20px 20px 20px 0;
    font-size: 24px;
    display: flex;
    justify-content: flex-end;
}
.contact-title-text{
    border-bottom: 2px solid rgb(100, 181, 246);
    padding: 2px 0;
    padding-left: 2px;
}

.contact-content{
    display: flex;
    flex-flow: column;
    align-items: flex-end;
    width: 100%;
}

.contact-item{
    display: flex;
    flex-flow: row;
    align-items: center;
    margin: 3px 0;
}

.contact-item-icon{
    padding-top: 3px;
    margin: 0 4px;
}

</style>
