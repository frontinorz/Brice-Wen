<template lang="pug">
.workscomp
    h1.title {{data.name}}
    .grid
        .img
        .desc {{data.desc}}
</template>

<script>
export default {
    props: {
        data: {
            type: Object,
            default:{},
            required: true,
        },
    }
}
</script>

<style lang="scss" scoped>
@import "./src/assets/style/_variable.scss";

.workscomp{
    display: grid;
    justify-content: center;
    padding-top: 2rem;
    grid-gap: 1rem;
}
.grid{
    display: grid;
    grid-auto-flow: column;
    grid-gap: 1rem;
    @include breakpoint(desktop){
        grid-auto-flow: row;
    }
}
.img{
    width: 500px;
    height: 500px;
    background: #eee;
}
.title{
    text-align: center;
    font-size: 2rem;
    color: #eee;
}
</style>
