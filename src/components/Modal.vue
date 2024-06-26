<template>
<div class="modal is-active">
  <div class="modal-background"></div>
  <div class="modal-content">
    <div class="box">
        <slot></slot>
    </div>
  </div>
  <button @click="closeModal" class="modal-close is-large" aria-label="close"></button>
</div>
</template>

<script setup>

const emit = defineEmits(['closeModal']);

function closeModal(){
    emit('closeModal');
}

</script>

<!-- <style scoped>
@import "https://cdn.jsdelivr.net/npm/bulma@1.0.0/css/bulma.min.css";
</style> -->