<template lang="pug">
#app
  siteHeader
  pageProfile#profile.sec
  pageSkill#skill.sec
  pageCareer#career.sec
  pageWorks#works.sec
  pageContact#contact.sec


</template>

<script>

import pageProfileVue from './component/pageProfile.vue';
import pageSkillVue from './component/pageSkill.vue';
import pageWorksVue from './component/pageWorks.vue';
import siteHeaderVue from './component/siteHeader.vue';
import pageCareerVue from './component/pageCareer.vue';
import pageContactVue from './component/pageContact.vue';

export default {
  name: 'app',
  components: {
    pageProfile: pageProfileVue,
    pageSkill: pageSkillVue,
    pageCareer: pageCareerVue,
    pageWorks: pageWorksVue,
    pageContact: pageContactVue,
    siteHeader: siteHeaderVue,
  },
  data () {
    return {
      secs: [],
    }
  },
  created() {
    const self = this;
    $(window).scroll(function() {
      $('.sec').each(function() {
        if(self.scrollNow(this)){
          $(this).addClass('inView');
        }
      });
    });

  },
  methods: {
    scrollNow(sec){
      const secTop = $(sec).offset().top;
      const winBot = $(window).scrollTop() + $(window).height();

      return winBot >= secTop * 1.2 ;
    }
  },
}
</script>

<style lang="scss">
@import "./src/assets/style/_variable.scss";

#app{
  width: 100%;
  min-width: 300px;
  font-family: 'Noto Sans','Microsoft JhengHei', Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.pagetitle{
    color: $color-hl-1;
    font-size: 2.5rem;
    letter-spacing: 5px;
    text-align: center;
    margin-bottom:3rem;
}
.pagetitle-odd{
  color: $color-hl-2;
}
.hr{
    width: 100%;
    height: 0.2rem;
    background: #aaa;
    margin-bottom: 1rem;
}
.active{
  background: #fff;
}

</style>
