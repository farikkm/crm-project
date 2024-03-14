<template>
  <section class="grid" style="min-height: 100vh;">
    <LayoutSidebar />
    <div>
      <slot></slot>
    </div>
  </section>
</template>

<script lang="ts" setup>

  console.log("Loaded");
</script>

<style scoped>
.grid {
  display: grid;
  grid-template-columns: 1fr 6fr;
}
</style>