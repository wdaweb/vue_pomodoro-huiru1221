<template>
  <v-app>
    <v-app-bar  :color="bgAppColor">
      <v-container class="d-flex align-center" >
        <v-app-bar-title>番茄鐘</v-app-bar-title>
        <div>
          <div></div>
          <div>
            <label>選擇主題顏色</label>
            <v-select
              v-model="bgAppColor"
              :items="colorOptions"
              label="選擇主題顏色"
              variant="outlined"
            ></v-select>
          </div>
        </div>
        <v-btn prepend-icon="mdi-home" to="/">首頁</v-btn>
        <v-btn prepend-icon="mdi-format-list-bulleted" to="/list">事項</v-btn>
        <v-btn prepend-icon="mdi-cog" to="/settings">設定</v-btn>
      </v-container>
    </v-app-bar>
    <v-main>
      <router-view v-slot="{ Component }">
        <keep-alive include="Home">
          <component :is="Component"></component>
        </keep-alive>
      </router-view>
    </v-main>
  </v-app>
</template>

<script setup>
import { ref } from 'vue'

const colorOptions = ['pink', 'blue', 'yellow', 'green']

const bgAppColor = ref('white')
</script>
