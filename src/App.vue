<template lang="pug">
#app
  pageProfile
  pageSkill
  pageCareer
  pageWorks
  pageContact
  siteFooter
</template>

<script>

import pageProfileVue from './component/pageProfile.vue';
import pageSkillVue from './component/pageSkill.vue';
import pageWorksVue from './component/pageWorks.vue';
import siteHeaderVue from './component/siteHeader.vue';
import siteFooterVue from './component/siteFooter.vue';
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
    siteFooter: siteFooterVue,
  },
  data () {
    return {

    }
  },
  methods: {

  },
}
</script>

<style lang="scss">
@import "./src/assets/style/_variable.scss";

#app{
  width: 100%;
  font-family: 'Microsoft JhengHei', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-size: 16px;
}

.pagetitle{
    color: $color-hl-1;
    font-size: 2.5rem;
    letter-spacing: 3px;
    font-weight: bold;
    text-align: center;
    margin-bottom:2rem;
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

</style>
