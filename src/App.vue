<template>

  <div>
    <a-drawer :is-open="isOpen" @close="isOpen = false"/>
    <a-header @toggle-drawer="toggleDrawer"/>
  </div>

</template>

<script setup lang="ts">
import AHeader from "@/components/AHeader.vue";
import ADrawer from "@/components/ADrawer.vue";
import {ref} from "vue";

const isOpen = ref(false);

const toggleDrawer = () => {
  isOpen.value = true;
}
</script>