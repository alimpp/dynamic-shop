<template>
  <div
    class="sidebar-content h-95-dvh flex flex-column"
    :class="{ 'w-250-px': isOpen, 'w-50-px': !isOpen }"
  >
    <div class="logo-content flex align-center justify-center">
      <img src="/public/logo/logo.png" alt="logo" width="100" />
    </div>
    <div class="routes-content flex flex-column">
      <LayoutsAdminRoutesContent
        :sidebarState="isOpen"
        @openSidebar="isOpen = true"
      />
    </div>
    <div class="w-100 flex justify-end" :class="{ 'justify-center': !isOpen }">
      <BaseIcon
        name="arrow-left"
        class="mx-10 cursor-pointer"
        v-if="isOpen"
        @click="isOpen = !isOpen"
      />
      <BaseIcon
        name="arrow-left"
        class="mx-10 cursor-pointer"
        v-else
        @click="isOpen = !isOpen"
      />
    </div>
  </div>
</template>

<script setup>
const isOpen = ref(false);
</script>

<style scoped>
.sidebar-content {
  border: 1px solid #00000016;
  border-radius: 10px;
  transition: 0.2s;
}
</style>
