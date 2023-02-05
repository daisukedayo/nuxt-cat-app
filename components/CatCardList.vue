<script lang="ts" setup>
import { CatResponse } from "~~/types/idnex";

interface Props {
  catDataList: CatResponse[];
}

defineProps<Props>();
</script>

<template>
  <!-- data-testidが親から流れてくる変数名？ -->
  <!-- 繰り返しの場合、「:key」が必要 -->
  <div class="cat-list" data-testid="cat-list">
    <!-- v-forでenumerateみたいなやつを記載できるので、ここでindexを作成。 -->
    <cat-card
      v-for="(cat, i) in catDataList"
      :key="i"
      :cat-data="cat"
    ></cat-card>
  </div>
</template>

<style scoped>
.card-list {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 16px;
}
</style>
