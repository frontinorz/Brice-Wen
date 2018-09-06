<template lang="pug">
.pageskill
    h1.pagetitle.pagetitle-odd SKILL
    .skill
        .group
            h2.title HTML
            .hr
            ul.list
                li.item 使用 Pug
                li.item 有 canvas 使用經驗
        .group
            h2.title CSS
            .hr
            ul.list
                li.item 使用 SASS
                li.item 熟悉 Flexbox
                li.item 熟悉 CSS Grid
                li.item 能不依賴 Framework 建置 RWD
                li.item 有 Bootstrap 使用經驗
        .group
            h2.title Javascript
            .hr
            ul.list
                li.item 有 ES6 基礎觀念
                li.item AJAX
                li.item 有介接第三方API經驗 (Google Maps, Youtube API)
        .group
            h2.title Vue.js
            .hr
            ul.list
                li.item 使用 Vue-Cli + Webpack 開發
                li.item 有 SPA 網頁經驗
        .group
            h2.title 開發環境
            .hr
            ul.list
                li.item VSCode
                li.item 有 Gulp 自動化經驗
                li.item 理解 Git / Github 基本指令運用
        .group
            h2.title 其他技能
            .hr
            ul.list
                li.item TOIEC  750
                li.item 熟悉 Photoshop
                li.item 基礎 Illustrator

</template>

<style lang="scss" scoped>
@import "./src/assets/style/_variable.scss";

.pageskill{
    color: #eee;
    background: $color-main-2;
    padding: 4rem $pd-desktop-lg;
    padding-bottom: 6rem;
    @include breakpoint(desktop){
        padding: 4rem $pd-desktop;
        padding-bottom: 6rem;
    }
    @include breakpoint(tablet){
        padding: 4rem $pd-tablet;
        padding-bottom: 6rem;
    }
    @include breakpoint(phone){
        padding: 4rem $pd-phone;
        padding-bottom: 6rem;
    }
}

.skill{
    display: grid;
    grid-gap: 2rem;
    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: repeat(3, 1fr);
    @include breakpoint(desktop-lg-re){
        grid-template-columns: repeat(3, 1fr);
        grid-template-rows: repeat(2, 1fr);
    }
    @include breakpoint(tablet){
        grid-gap: 1rem;
    }
    @include breakpoint(phone){
        grid-template-columns: 1fr;
        grid-template-rows: repeat(6, 1fr);
    }
}
.group{
    padding: 1rem;
    position: relative;
    background: rgba(255,255,255,0.1);
    opacity: 0;
}

.list{
    margin-left: 0.5rem;
}
.item{
    font-size: 1.1rem;
    margin-bottom: 0.2rem;
    &:before{
        content: '-';
        margin-right: 0.2rem;
    }
}
.title{
    font-size: 1.5rem;
    font-weight: bold;
    margin-bottom: 1rem;
}

.inView{
    .group{
        animation: fadeIn 0.8s  both;

        @for $i from 0 to 6{
            &:nth-child(#{$i+1}){
                animation-delay: $i*0.3s
            }
        }

        @include breakpoint(tablet){
            @for $i from 0 to 6{
                &:nth-child(#{$i+1}){
                    animation-delay: $i*0.6s
                }
            }
        }
    }
}

@keyframes fadeIn {
    0%{opacity: 0; transform: translateY(-1rem);}
    100%{opacity: 1; transform: translateY(0rem);}
}
</style>
