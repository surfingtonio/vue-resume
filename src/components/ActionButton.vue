<template>
  <div class="action-button action-button--show" @click="handleClick">
    <font-awesome-icon
      :icon="['fas', 'print']"
      class="icon icon--action-button"
    />
  </div>
</template>

<script>
export default {
  name: "ActionButton",
  methods: {
    handleClick() {
      window.print();
    },
  },
};
</script>
