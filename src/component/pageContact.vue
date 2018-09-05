<template lang="pug">
.pagecontact
    .pagetitle.pagetitle-odd CONTACT
    .contact
        .linkgroup
            a(href="https://github.com/frontinorz" target="_blank")
                i.fab.fa-github
            a(href="https://codepen.io/frontinorz/" target="_blank")
                i.fab.fa-codepen
        a.email(href="mailto:frontinorz@gmail.com") frontinorz@gmail.com
    .foot © Brice Wen 2018
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
@import "./src/assets/style/_variable.scss";
.pagecontact{
    width: 100%;
    position: relative;
    display: grid;
    align-items: center;
    background: $color-main-1;
    padding: 2rem $pd-desktop-lg;
    color: #eee;
    @include breakpoint(desktop){
        padding: 2rem $pd-desktop;
    }
    @include breakpoint(tablet){
        padding: 2rem $pd-tablet;
    }
    @include breakpoint(phone){
        padding: 2rem $pd-phone;
    }
}

.contact{
    height: 100%;
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    margin-bottom: 2rem;
}

.linkgroup{
    a{
        margin: 0;
        &:first-child{
            margin-right: 2rem;
        }
    }
    i{
        cursor: pointer;
        font-size: 4rem;
        margin: 0;
        &:hover{
            color: lighten($color-main-2, 20);
        }
    }
}

.email{
    margin-top: 1.5rem;
    font-size: 1.6rem;
    letter-spacing: 1px;
    &:hover{
        color: lighten($color-main-2, 20);
    }
}
.foot{
    text-align: center;
    align-self: end
}

</style>
