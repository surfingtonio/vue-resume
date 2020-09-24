<template>
  <ul class="section__items">
    <li
      class="section__item"
      v-for="item in items"
      :key="item.company"
    >
      <OrderedListItem v-bind="item" />
    </li>
  </ul>
</template>

<script>
import OrderedListItem from '@/components/OrderedListItem.vue';

export default {
  name: 'OrderedList',
  components: {
    OrderedListItem,
  },
  props: {
    items: {
      type: Array,
      required: true,
    },
  },
};
</script>