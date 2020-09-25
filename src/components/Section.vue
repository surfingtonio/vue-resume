<template>
  <section class="section" :class="defaultClassNames">
    <h2 class="section__title" v-if="title">{{ title }}</h2>
    <slot></slot>
  </section>
</template>

<script>
export default {
  name: "Section",
  props: {
    title: {
      type: String,
      required: false,
    },
  },
  computed: {
    defaultClassNames: function () {
      // This component does not render on mobile devices
      // when using a version of Chrome less than 85.0.4183.127
      // or Samsung Internet version 12.1.2.5 apparently
      // because of the call to the javascript replaceAll() method.
      let words =
        this.title === undefined ? [] : this.title.toLowerCase().split(/\s/);
      return words.join("-");
    },
  },
};
</script>
