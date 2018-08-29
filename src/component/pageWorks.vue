<template lang="pug">
.pageworks
    .pagetitle WORKS
    .works
        .btn.btn__prev(@click="pageFlip(-1)")
            i.fas.fa-angle-left
        .workscontent
            transition(name="page" mode="out-in")
                workscomp(:data="now", :key="now")
        .btn.btn__next(@click="pageFlip(1)")
            i.fas.fa-angle-right
</template>

<script>
import WorkscompVue from './Workscomp.vue';
const workslist = [
    {
        name: 'Workoutube',
        img: '',
        desc: '健身APP',
    },
    {
        name: '新竹UBike',
        img: '',
        desc: '新竹UBike查詢',
    },
    {
        name: '個人網站',
        img: '',
        desc: '個人網站',
    },
];

export default {
    name: 'pageworks',
    components: {
        workscomp: WorkscompVue,
    },
    data(){
        return {
            list: workslist,
            now: workslist[0],
            index: 0,
        }
    },
    methods:{
        pageFlip(dir){
            this.index += dir
            if( this.index > 2 ) this.index=0
            if( this.index < 0 ) this.index=2
            this.now = workslist[this.index]
        }
    }
}
</script>

<style lang="scss" scoped>
@import "./src/assets/style/_variable.scss";

.pageworks{
    color: #eee;
    min-height: 100vh;
    position: relative;
    background: $color-main-2;
    padding: 4rem $pd-desktop-lg;
    @include breakpoint(desktop){
        padding: 4rem $pd-desktop;
    }
    @include breakpoint(tablet){
        padding: 3rem $pd-tablet;
    }
}
.works{
    width: 100%;
    height: 80vh;
    display: grid;
    grid-template-columns: 3rem 1fr 3rem;
    grid-gap: 1rem;
}

.btn{
    font-size: 2.5rem;
    text-align: center;
    align-self: center;
    width: 3rem;
    cursor: pointer;
    &:hover{
        color: $color-hl-2;
    }
}
.btn__prev{
    transition: transform 0.3s;
    &:hover{
        transform: translateX(-0.5rem);
    }
}
.btn__next{
    transition: transform 0.3s;
    &:hover{
        transform: translateX(0.5rem);
    }
}

.page-enter-active, .page-leave-active{
    transition: 0.3s cubic-bezier(0, 0, 0, 1);
}
.page-leave-to{
    transform: translateY(20px);
    opacity: 0;
}
.page-enter{
    transform: translateY(-20px);
    opacity: 0;
}
</style>
