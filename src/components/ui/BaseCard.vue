<template>
  <div class="card">
    <slot></slot>
  </div>
</template>

<style scoped>
/* Obsah z base-card.css */
.card {
  max-width: 40rem;
  margin: auto;
  padding: 1rem;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  border-radius: 12px;
  background-color: white;
}
</style>
