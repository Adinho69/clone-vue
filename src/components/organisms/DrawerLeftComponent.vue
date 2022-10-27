<script setup lang="ts">
import { hasDynamicKeyVBind } from "@vue/compiler-core";
import { ref } from "vue";

const leftDrawerOpen = ref(false);
</script>

<template>
  <q-drawer show-if-above v-model="leftDrawerOpen" side="left" bordered>
    <!-- drawer content -->

    <q-scroll-area class="fit">
      <div id="menu" style="height: 200px; background: #345"></div>
      <div class="q-pa-sm">
        <div v-for="n in 50" :key="n">Drawer {{ n }} / 50</div>
      </div>
    </q-scroll-area>
  </q-drawer>
</template>

<style scoped>
#menu {
  position: sticky;
  top: 0;
  margin-top: 30px;
  padding: 20px;
  background-color: #000;
  color: #fff;
}
</style>
