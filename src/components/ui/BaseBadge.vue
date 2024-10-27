<template>
  <span :class="['badge', typeClass]">{{ text }}</span>
</template>

<script>
export default {
  props: {
    type: { type: String, required: true },
    title: { type: String, required: true },
  },
  computed: {
    text() {
      return this.title.toUpperCase();
    },
    typeClass() {
      return this.type;
    },
  },
};
</script>

<style scoped>
/* Obsah z base-badge.css */
.badge {
  display: inline-block;
  padding: 0.25rem 0.75rem;
  font-size: 0.75rem;
  font-weight: bold;
  color: white;
  border-radius: 4px;
}
.frontend {
  background-color: #42a5f5;
}
.backend {
  background-color: #8e44ad;
}
.career {
  background-color: #ff8c00;
}
</style>
