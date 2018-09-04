<template lang="pug">
.siteheader
    .top
        .icon
        .burger(@click="isList = !isList", :class="{'listopen' : isList}")
            .line
            .line
            .line
    .overlay(:class="{'overlay__active' : isList}")
        .list
            a.sectag(href="#profile"  @click="isList = !isList") PROFILE
            a.sectag(href="#skill" @click="isList = !isList") SKILL
            a.sectag(href="#career" @click="isList = !isList") CAREER
            a.sectag(href="#works" @click="isList = !isList") WORKS
            a.sectag(href="#contact" @click="isList = !isList") CONTACT
</template>

<script>

export default {
    name: 'siteHeader',
    data () {
        return {
            isList: false,
        }
    },
    created() {
        $(document).on('click','.sectag',function(event){
            event.preventDefault();
            let target = $(this).attr("href");
            this.isList = false;
            console.log(this.isList);
            $('html,body').animate({
                scrollTop: $(target).offset().top
            },600);
        });
    },
    methods: {
        toogleList(){
            this.isList = false;
        }
    },
}
</script>

<style lang="scss" scoped>
@import "./src/assets/style/_variable.scss";

.siteheader{
    position: fixed;
    width: 100%;
    height: 20vh;
    padding: 2rem;
    color: #eee;
    z-index: 50;
}
.top{
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.burger{
    position: relative;
    display: flex;
    justify-content: space-between;
    flex-direction: column;
    width: 2rem;
    height: 1.5rem;
    z-index: 50;
    cursor: pointer;
    &:hover{
        .line:nth-child(2){
            width: 100%;
        }
    }
}
.line{
    background: #eee;
    height: 3px;
    transition: transform 0.3s;
    &:first-child{
        width: 100%;
    }
    &:nth-child(2){
        width: 60%;
        transition: width 0.3s;
    }
    &:last-child{
        width: 100%;
    }
}
.listopen{
    &:hover{
        .line:nth-child(2){
            width: 0%;
        }
    }
    .line{
        &:first-child{
            width: 100%;

            transform: translateY(0.65rem) rotate(45deg);
        }
        &:nth-child(2){
            width: 0%;
            transition: width 0.3s;
        }
        &:last-child{
            width: 100%;
            transform: translateY(-0.65rem) rotate(-45deg);
        }
    }
}
.overlay{
    position: absolute;
    width: 100vw;
    height: 100vh;
    left: 0;
    top: 0;
    background:  $color-hl-2;
    opacity: 0;
    display: flex;
    align-items: center;
    justify-content: center;;
    transition: opacity 0.3s;
    z-index: -100;
    pointer-events: none;
    &__active{
        opacity: 1;
        z-index: 10;
        pointer-events: all;
    }
}
.list{
    width: 50%;
    height: 60%;
    display: flex;
    align-items: center;
    justify-content: space-around;
    flex-direction: column;
    a{
        position: relative;
        font-size: 2rem;
        font-weight: bold;
        letter-spacing: 0.1rem;
        &:before{
            content: '';
            position: absolute;
            left: -10%;
            top: 50%;
            width: 0%;
            height: 4px;
            background: $color-main-1;
            transition: width 0.3s;
        }
        &:hover{
            &:before{
                width: 120%;
            }
        }
    }
}
</style>
