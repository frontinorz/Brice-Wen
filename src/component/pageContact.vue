<template lang="pug">
.pagecontact
    .pagetitle.pagetitle-odd CONTACT
    .contact
        .linkgroup
            a(href="https://github.com/frontinorz" target="_blank")
                i.fab.fa-github
            a(href="https://codepen.io/frontinorz/" target="_blank")
                i.fab.fa-codepen
        .email frontinorz@gmail.com
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
@import "./src/assets/style/_variable.scss";

.pagecontact{
    width: 100%;
    height: 50vh;
    background: $color-main-1;
    padding: 4rem $pd-desktop-lg;
    color: #eee;
    @include breakpoint(desktop){
        padding: 4rem $pd-desktop ;
    }
}

.contact{
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
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
        font-size: 5rem;
        margin: 0;
        //transition: color 0.1s;
        &:hover{
            color: lighten($color-main-2, 20);
        }
    }
}

.email{
    margin-top: 1.5rem;
    font-size: 2rem;
}

</style>
