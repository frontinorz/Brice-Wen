<template lang="pug">
.pagecareer
    h1.pagetitle CAREER
    //.hr
    .career
        .time
            .time__date 2014 / 7 ─ 2014 / 9
            .time__date 2014 / 9 ─ 2015 / 5
            .time__date 2016 / 8 ─ 2018 / 2
        .timeline
            .dotgroup
                .dot
                .dot
                .dot
        .job
            .job__group
                h4.job__date 2014 / 7 ─ 2014 / 9
                h2.job__title 彩天科技
                h3.job__pos 多媒體程式設計實習生
            .job__group
                h4.job__date 2014 / 9 ─ 2015 / 5
                h2.job__title 《小王紙》Unity3D繪本解謎遊戲
                h3.job__pos 程式 / 企劃
            .job__group
                h4.job__date 2016 / 8 ─ 2018 / 2
                h2.job__title 自家營業裝潢工程行
                h3.job__pos 室內設計助理 / 木工學徒


</template>


<style lang="scss" scoped>
@import "./src/assets/style/_variable.scss";
.pagecareer{
    background: $color-main-1;
    padding: 4rem $pd-desktop-lg;
    padding-bottom: 12rem;
    @include breakpoint(desktop){
        padding: 4rem $pd-desktop;
        padding-bottom: 12rem;
    }
    @include breakpoint(tablet){
        padding: 4rem $pd-tablet;
        padding-bottom: 8rem;
    }
    @include breakpoint(phone){
        padding: 4rem $pd-phone;
        padding-bottom: 8rem;
    }
}
.career{
    color: #eee;
    display: grid;
    grid-auto-rows: auto auto auto;
    text-align: center;
    margin-top: 8rem;
    grid-gap: 3rem;
    @include breakpoint(tablet){
        grid-auto-rows: auto
    }
    @include breakpoint(phone){
        padding: 2rem $pd-phone;
    }
}
.time{
    width: 100%;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    align-items: center;
    justify-items: center;
    &__date{
        display: grid;
        justify-items: center;
        font-size: 1.2rem;
        opacity: 0;
        @include breakpoint(tablet){
            margin-bottom: 0;
        }
    }
    @include breakpoint(tablet){
        display: none;
    }
}
.timeline{
    width: 0%;
    position: relative;
    height: 0.2rem;
    background: #eee;
    .dotgroup{
        width: 100%;
        position: absolute;
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        align-items: center;
        justify-items: center;
        transform: translateY(-0.3rem);
    }
    .dot{
        width: 0.8rem;
        height: 0.8rem;
        border-radius: 100%;
        position: relative;
        background: $color-sub-1;
        opacity: 0;
        &:after{
            content: '';
            position: absolute;
            left: 50%;
            top: 50%;
            transform: translate(-50%,-50%);
            width: 1.5rem;
            height: 1.5rem;
            border-radius: 100%;
            background: $color-sub-1;
            opacity: 0.3;
            z-index: -2;
        }
        @include breakpoint(tablet){
            //display: none;
        }
    }
    @include breakpoint(tablet){
        display: none;
    }
}

.job{
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-gap: 2rem;
    @include breakpoint(tablet){
        grid-template-columns: 1fr;
        grid-gap: 5rem;
    }
    &__date{
        display: none;
        color: rgb(185, 185, 185);
        @include breakpoint(tablet){
            display: block;
            margin-bottom: 1rem;
        }
    }
    &__group{
        display: grid;
        width: 100%;
        grid-auto-rows: 1fr 1fr;
        align-items: center;
        justify-items: center;
        opacity: 0;
        position: relative;
        @include breakpoint(tablet){
            grid-auto-rows: auto 1fr 1fr;
            @for $i from 0 to 2{
                &:nth-child(#{$i+1}){
                    &:after{
                        content: '';
                        position: absolute;
                        width: 0.2rem;
                        height: 3rem;
                        background: $color-sub-1;
                        bottom: 0;
                        transform: translateY(125%);
                    }
                }
            }


        }
    }
    &__title{
        font-size: 1.3rem;
        letter-spacing: 1px;
        font-weight: bold;
        margin-bottom: 1rem;
        @include breakpoint(tablet){
            margin-bottom: 0.2rem;
        }
    }
    &__pos{
        font-size: 1.1rem;
    }

}
.inView{
    .timeline{
        animation: timelinegrow 1s both;
    }
    .dot{
        @for $i from 0 to 3{
            &:nth-child(#{$i+1}){
                animation: fadeIn 0.3s 1+$i*0.3s both;
            }
        }
    }
    .time__date{
        @for $i from 0 to 3{
            &:nth-child(#{$i+1}){
                animation: fadeIn-Top 0.3s 2+$i*0.3s both;
            }
        }
    }
    .job__group{
        @for $i from 0 to 3{
            &:nth-child(#{$i+1}){
                animation: fadeIn-Bot 0.3s 2+$i*0.3s both;
            }
        }
        @include breakpoint(tablet){
            &:nth-child(1){
                animation: fadeIn 0.3s both;
                &:after{
                    animation: timelinegrow-m 0.3s 0.5s both;
                }
            }
            &:nth-child(2){
                animation: fadeIn 0.3s 1s both;
                &:after{
                    animation: timelinegrow-m 0.3s 1.5s both;
                }
            }
            &:last-child{
                animation: fadeIn 0.3s 2s both;
            }
        }
    }
}

@keyframes timelinegrow {
    0%{ width: 0; }
    100%{ width: 100%; }
}
@keyframes timelinegrow-m {
    0%{ height: 0; }
    100%{ height: 3rem; }
}
@keyframes fadeIn {
    0%{ opacity: 0; }
    100%{ opacity: 1; }
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
