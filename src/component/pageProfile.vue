<template lang="pug">
.profile
    .about
        img.myimg(:src="imgurl")
        .name
            h1.name__cht 温志桓
            h3.name__eng Brice
        .info
            i.icon.fas.fa-map-marker-alt
            span.city 新竹
    .desciption
        p 喜愛任何形式的創作
        p 程式、木作、音樂、攝影
        p 從構思直至成型的作品
        p 享受突破各個階段帶來的滿足感
        p 現階段沉浸在網頁前端技術
</template>

<script>
export default {
    name: 'pageprofile',
    data(){
        return {
            imgurl: './dist/self.jpg',
        }
    },
}
</script>

<style lang="scss" scoped>
@import "./src/assets/style/_variable.scss";

.profile{
    width: 100%;
    min-height: 100vh;
    padding-top: 20vh;
    background: $color-main-1;
    color: #eee;
    display: flex;
    align-items: center;
    flex-direction: column;
    text-align: center;
}
.about{
    margin-bottom: 1rem;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    animation: fadeIn-Top 1s both;
}
.myimg{
    border-radius: 50%;
    width: calc(100vw / 5);
    height: calc(100vw / 5);
    max-width: 150px;
    max-height: 150px;
    min-width: 100px;
    min-height: 100px;
    object-fit: cover;
    margin-bottom: 0.5rem;
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
    color: #aaa;
}
.icon{
    margin-right: 0.5rem;
}

.desciption{
    animation: fadeIn-Bot 1s 0.5s both;
    p{
        margin-bottom: 0.2rem;
        letter-spacing: 1px;
    }
}

@keyframes fadeIn-Top {
    0%{ opacity: 0; transform: translateY(-1rem);}
    100%{ opacity: 1; transform: translateY(0);}
}
@keyframes fadeIn-Bot {
    0%{ opacity: 0; transform: translateY(1rem);}
    100%{ opacity: 1; transform: translateY(0);}
}
</style>
