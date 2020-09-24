<template>
  <h3 class="section__item-title ordered-list__title">
    {{ title }}
  </h3>
  <h4 class="ordered-list__company">{{ company }}</h4>
  <a
    v-if="url"
    :href="url"
    class="ordered-list__url"
    target="_blank"
  >
    {{ url }}
  </a>
  <div class="ordered-list__term">
    <span class="start">{{ start.getFullYear() }}</span> –
    <span v-if="end" class="end">{{ end.getFullYear() }}</span
    ><span v-else class="end">Present</span>
  </div>
  <div class="ordered-list__details">
    <p v-if="details">{{ details }}</p>
    <ul>
      <li v-for="item in items" :key="item">
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'OrderedListItem',
  props: {
    title: {
      type: String,
      required: true,
    },
    company: {
      type: String,
      required: true,
    },
    url: {
      type: String,
      required: false,
    },
    start: {
      type: Date,
      required: true,
    },
    end: {
      type: Date,
      required: false,
    },
    details: {
      type: String,
      required: false,
    },
    items: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped></style>
