<template lang="pug">
.pagecareer
    .pagetitle CAREER
    //.hr
    .career
        .group
            .time 2012 / 7 ─ 2016 / 7
            .timeline
            .title
                .subtitle 元智大學─資訊傳播學系
                .subtitle
                    a(href="https://youtu.be/ZiYNX9rny78") 《小王紙》
                    span Unity3D繪本解謎遊戲
            .job 程式設計 / 遊戲企劃
            ul.detail
                li 腳色控制、事件觸發
        .group
            .time 2015 / 7 ─ 2015 / 8
            .timeline
            .title 彩天科技
            .job 多媒體程式設計實習生
            ul.detail
                li 使用 Unity 開發觸控相片牆
                li Resolume Arena 光雕軟體操作
        .group
            .time 2016 / 8 ─ 2018 / 2
            .timeline
            .title 自家營業裝潢工程行
            .job 室內設計助理 / 木工學徒
            ul.detail
                li 使用 SketchUp 繪製設計圖
                li 設計提案及業務溝通
                li 木工實作

</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
@import "./src/assets/style/_variable.scss";
.pagecareer{
    min-height: 100vh;
    background: $color-main-1;
    padding: 4rem $pd-desktop-lg;
    @include breakpoint(desktop){
        padding: 4rem $pd-desktop ;
    }
}
.career{
    color: #eee;
    display: grid;
    grid-auto-flow: column;
    grid-auto-columns: 1fr 1fr 1fr;
    text-align: center;
    padding-top: 5rem;
    padding-bottom: 5rem;
}
.group{
    display: grid;
    width: 100%;
    grid-auto-rows: 1fr 1fr 1fr 1fr 1fr;
    align-items: center;
    justify-items: center;
}
.time{
    font-size: 1.2rem;
    margin-bottom: 2rem;
}
.timeline{
    width: 100%;
    height: 0.1rem;
    background: #aaa;
    margin-bottom: 2rem;
    position: relative;
    &:before{
        content: '';
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%,-50%);
        width: 1rem;
        height: 1rem;
        border-radius: 100%;
        background: $color-sub-1;
    }
}
.title{
    font-size: 1.3rem;
    letter-spacing: 1px;
    font-weight: bold;
}
.job{
    font-size: 1.1rem;
}
.detail{
    //text-align: left;
    align-self: start;
}

</style>
