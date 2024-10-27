<template>
  <button v-if="!link" :class="modeClass"><slot></slot></button>
  <router-link v-else :to="to" :class="modeClass"><slot></slot></router-link>
</template>

<script>
export default {
  props: {
    link: { type: Boolean, default: false },
    to: { type: String, default: '/' },
    mode: { type: String, default: '' },
  },
  computed: {
    modeClass() {
      return this.mode ? this.mode : '';
    },
  },
};
</script>

<style scoped>
/* Obsah z base-button.css */
button,
a {
  display: inline-block;
  padding: 0.5rem 1.5rem;
  border-radius: 4px;
  background-color: #ff6b6b;
  color: white;
  text-decoration: none;
}
button.outline,
a.outline {
  background-color: transparent;
  border: 1px solid #ff6b6b;
  color: #ff6b6b;
}
button.flat,
a.flat {
  background-color: transparent;
  color: #ff6b6b;
}
</style>
