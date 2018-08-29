<template lang="pug">
.profile
    //.bgimg
    .about
        .picture
        .name
            h1.name__cht 溫志桓
            h3.name__eng Brice
        .info
            //h4.school 元智大學─資訊傳播學系
            i.icon.fas.fa-map-marker-alt
            span.city 新竹
    .desciption
        p 喜愛任何形式的創作
        p 程式、木作、音樂、攝影
        p 從構思直至成型的作品
        p 享受突破各個階段帶來的滿足感
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
@import "./src/assets/style/_variable.scss";
.bgimg{
    width: 100%;
    min-height: 100vh;
    position: fixed;
    left: 0;
    top: 0;
    background-image: url('~/src/assets/bg.jpg');
    filter: brightness(80%);
    background-size: cover;
    background-position: center center;
    z-index: -5;
}
.profile{
    width: 100%;
    min-height: 100vh;
    padding-top: 20vh;
    background: $color-main-1;
    //background: transparent;;
    color: #eee;
    display: flex;
    align-items: center;
    flex-direction: column;
    text-align: center;
}
.about{
    margin-bottom: 1rem;
}
.picture{
    width: 150px;
    height: 150px;
    background: #eee;
    border-radius: 100%;
    margin-bottom: 1rem;
}
.name{
    margin-bottom: 0.5rem;
    &__cht{
        font-size: 2rem;
        letter-spacing: 2px;
    }
    &__eng{
        margin-top: -5px;
        font-size: 1.5rem;
        letter-spacing: 1px;
    }
}
.info{
    margin-bottom: 1rem;
}
.school{
    margin-bottom: 0.2rem;
}
.icon{
    margin-right: 0.5rem;
}

.desciption{
    p{
        margin-bottom: 0.2rem;
        letter-spacing: 1px;
    }
}
</style>
