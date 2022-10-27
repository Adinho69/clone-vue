<script setup lang="ts">
import { ref } from "vue";
import DrawerFelt from "../components/organisms/DrawerLeftComponent.vue";

const rightDrawerOpen = ref(false);
</script>

<template>
  <q-layout view="hHh lpR fFf">
    <q-header class="bg-white text-black" bordered>
      <q-toolbar class="q-px-xl row justify-start">
        <q-toolbar-title class="text-body1 item-end col-1">
          <q-avatar>
            <img src="../assets/logoVue.png" />
          </q-avatar>
          Vue.js
        </q-toolbar-title>
        <div class="row col-11">
          <q-button class="header-busca col-3">
            <span class="icon">
              <svg
                width="20"
                height="20"
                class="DocSearch-Search-Icon"
                viewBox="0 0 20 20"
              >
                <path
                  d="M14.386 14.386l4.0877 4.0877-4.0877-4.0877c-2.9418 2.9419-7.7115 2.9419-10.6533 0-2.9419-2.9418-2.9419-7.7115 0-10.6533 2.9418-2.9419 7.7115-2.9419 10.6533 0 2.9419 2.9418 2.9419 7.7115 0 10.6533z"
                  stroke="currentColor"
                  fill="none"
                  fill-rule="evenodd"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                ></path>
              </svg>
              <span>Search</span>
            </span>
            <span class="atalho">Ctrl K</span>
          </q-button>

          <div class="col-6">Tab</div>
          <div class="col-1">Toggle</div>
          <div class="col-2">Rede sociais</div>
        </div>
      </q-toolbar>
    </q-header>

    <DrawerFelt />

    <q-drawer show-if-above v-model="rightDrawerOpen" side="right" bordered>
      <!-- drawer content -->
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<style lang="scss" scoped>
.header-busca {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  opacity: 0.2;

  .icon {
    display: flex;
    align-items: center;
    justify-content: center;
    span {
      padding: 0px 10px;
    }
  }

  .atalho {
    padding: 0 6px;
    border: 2px solid #871;
    border-radius: 5px;
  }

  &:hover {
    opacity: 1;
    transition: 0.7s;
  }
}
</style>
