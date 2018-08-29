<template lang="pug">
.pageskill
    .pagetitle.pagetitle-odd SKILL
    //.hr
    .skill
        .group
            .title HTML
            .hr
            ul.list
                li.item 使用 Pug
                li.item 有 canvas 使用經驗
        .group
            .title CSS
            .hr
            ul.list
                li.item 使用 SASS
                li.item 熟悉 Flexbox
                li.item 熟悉 CSS Grid
                li.item 能不依賴 Framework 建置 RWD
                li.item 有 Bootstrap 使用經驗
        .group
            .title Javascript
            .hr
            ul.list
                li.item 使用 ES6
                li.item AJAX
                li.item 有介接第三方API經驗 (Google Map, Youtube API)
        .group
            .title Vue.js
            .hr
            ul.list
                li.item 使用 Vue-Cli + Webpack 開發
                li.item 有 SPA 網頁經驗
        .group
            .title 開發環境
            .hr
            ul.list
                li.item VSCode
                li.item 使用 Gulp 進行自動化
                li.item 理解 Git / Github 基本指令運用
        .group
            .title 其他工具
            .hr
            ul.list
                li.item TOIEC  750
                li.item 熟悉 Photoshop
                li.item 基礎 Illustrator

</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
@import "./src/assets/style/_variable.scss";

.pageskill{
    color: #eee;
    background: $color-main-2;
    padding: 4rem $pd-desktop-lg;
    padding-bottom: 10rem;
    @include breakpoint(desktop){
        padding: 4rem $pd-desktop ;
    }
}

.skill{
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: 1fr 1fr;
    grid-gap: 2rem;
}
.group{
    padding: 1rem;
    position: relative;
    background: rgba(255,255,255,0.1);
}
@for $i from 0 to 5{
    .group:nth-child(#{$i+1}){

    }
}
.list{
    margin-left: 0.5rem;
}
.item{
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
</style>
