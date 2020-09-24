<template>
  <Section class="section--footer footer">
    <span class="footer__item">
      Made with
      <a href="https://vuejs.org" target="_blank" class="url">Vue.js</a>
    </span>
    <span class="footer__item footer__item--info" v-if="info">{{ info }}</span>
  </Section>
</template>

<script>
import Section from "@/components/Section.vue";

export default {
  name: "Footer",
  components: {
    Section,
  },
  props: {
    info: {
      type: String,
      required: false,
    },
  },
};
</script>
