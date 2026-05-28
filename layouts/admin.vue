<!-- <template>
  <div class="flex w-100 overflow-hidden">
    <div class="sidebar-container flex">
      <LayoutsAdminSidebar
        :isOpen="sidebarState"
        @handleChangeSidebarState="handleChangeSidebarState"
      />
    </div>

    <div
      :style="{
        width: sidebarState ? 'calc(100% - 250px)' : 'calc(100% - 50px)',
      }"
      class="px-20 h-100-dvh flex flex-column"
    >
      <LayoutsAdminTopbar />
      <div class="page-content flex mt-10">
        <NuxtPage />
      </div>
    </div>
  </div>
</template>



<style scoped>
.page-content {
  min-height: 90dvh;
  max-height: 90dvh;
  overflow-y: scroll;
  background: red;
}
</style> -->

<template>
  <div class="layout-container">
    <div class="sidebar-container">
      <LayoutsAdminSidebar
        :isOpen="sidebarState"
        @handleChangeSidebarState="handleChangeSidebarState"
      />
    </div>

    <div class="main-content">
      <header class="topbar-container">
        <LayoutsAdminTopbar />
      </header>

      <main class="page-content">
        <NuxtPage />
      </main>
    </div>
  </div>
</template>

<script setup>
const sidebarState = ref(true);

const handleChangeSidebarState = (val) => {
  sidebarState.value = val;
};
</script>

<style scoped>
.layout-container {
  display: flex;
  height: 100vh;
  overflow: hidden;
}

.sidebar-container {
  flex-shrink: 0;
  background-color: #f4f4f4;
}

.main-content {
  flex-grow: 1;
  display: flex;
  flex-direction: column;
  overflow: hidden;
  padding: 10px;
}

.topbar-topbar-container {
  height: 60px;
  flex-shrink: 0;
  background-color: #fff;
  border-bottom: 1px solid #ddd;
}

.page-content {
  flex-grow: 1;
  overflow-y: auto;
  padding: 5px 0;
}
.page-content::-webkit-scrollbar {
  display: none;
}
</style>
