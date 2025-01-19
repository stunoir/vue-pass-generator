<script setup>
  import PasswordGenerator from './components/PasswordGenerator.vue'
</script>

<template>
  <div class="page-container">
    <div class="grid-container">
      <div class="grid-x grid-padding-x align-center">
        <div class="cell medium-6">
          <PasswordGenerator></PasswordGenerator>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
  .page-container {
    padding: 3rem 0;
  }
</style>
