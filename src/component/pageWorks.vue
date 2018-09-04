<template lang="pug">
.pageworks
    .pagetitle WORKS
    .works
        .work(v-for="work in list")
            img.work__img(:src="work.img")
            .work__info
                .work__name {{ work.name }}
                .work__detail
                    .work__desc {{ work.desc }}
                    ul.work__tech
                        li(v-for="item in work.tech") {{ item }}
                    a.work__link(:href="work.link" target="_blank") 作品連結
</template>

<script>


const workslist = [
    {
        name: 'Workoutube',
        img: '/dist/workoutube.jpg',
        desc: '運用Youtube作為輔助，快速建立自己的健身筆記',
        tech: ['RWD','Vue-cli SPA','Vue-youtube','Localstorage'],
        link: 'https://frontinorz.github.io/workoutube/#/'
    },
    {
        name: '新竹UBike',
        img: '/dist/ubike.jpg',
        desc: '運用Google Map及衛星定位快速找查附近的Youbike站點',
        tech: ['RWD','Vue.js','HTML5 Geolocation','Google Maps API'],
        link: 'https://frontinorz.github.io/Google-map/'
    },
];

export default {
    name: 'pageworks',
    data(){
        return {
            url: '../assets/workoutube.jpg',
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
    //min-height: 100vh;
    position: relative;
    background: $color-main-2;
    padding: 4rem $pd-desktop;
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
.works{
    width: 100%;
    height: 100%;
    display: grid;
    align-items: center;
    justify-content: center;
    grid-template-columns: 1fr 1fr;
    grid-gap: 1rem;
    @include breakpoint(desktop){
        grid-template-columns: 1fr;
        grid-template-rows: 1fr 1fr;
    }
    @include breakpoint(phone){
        padding: 2rem $pd-phone;
    }
}
.work{
    text-align: center;
    position: relative;
    overflow: hidden;
    background: #eee;
    opacity: 0;
    &:hover{
        .work__info{
            transform: translateY(0%);
            opacity: 1;
        }
        .work__name{
            transform: translateY(0%);
        }
        .work__detail{
            transform: translateY(0%);
        }
    }
        &__img{
            width: 100%;
            height: 100%;
        }
        &__info{
            position: absolute;;
            width: 100%;
            height: 100%;
            left: 0;
            top: 0;
            padding: 2rem;
            background: rgba(black,0.8);
            opacity: 0;
            transition: opacity 0.3s cubic-bezier(0, 0, 0.2, 1);
            @include breakpoint(tablet){
                padding: 1rem;
            }
        }
        &__name{
            font-size: 1.5rem;
            margin-bottom: 1rem;
            font-weight: bold;
            transform: translateY(-20%);
            transition: transform 0.3s cubic-bezier(0, 0, 0.2, 1);
        }
        &__detail{
            height: 80%;
            display: grid;
            align-items: center;
            justify-content: center;
            grid-gap: 1rem;
            transform: translateY(5%);
            transition: transform 0.3s cubic-bezier(0, 0, 0.2, 1);
        }
        &__desc{

        }
        &__tech{
            li{
                margin-bottom: 0.2rem;
                @include breakpoint(phone){
                    &:first-child{
                        display: none;
                    }
                }
            }
        }
        &__link{
            align-self: end;
            font-weight: bold;
            letter-spacing: 2px;
            justify-self: center;
            padding: 0.3rem 1rem;
            background: $color-hl-2;
            transition: background 0.3s;
            &:hover{
                background: darken($color-hl-2, 10);
            }
        }
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
.inView{
    .work{
        animation: fadeIn-Top 0.3s both;
        &:nth-child(2){
            animation-delay: 0.3s;
        }
    }
}

@keyframes fadeIn-Top {
    0%{ opacity: 0; transform: translateY(-1rem);}
    100%{ opacity: 1; transform: translateY(0);}
}
</style>
