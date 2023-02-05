<script lang="ts" setup>
import { CatResponse } from "~~/types/idnex";

const { pending, error, data } = useFetch<CatResponse[]>(
  "https://api.thecatapi.com/v1/images/search?limit=10"
);
</script>

<template>
  <!-- <div>Page: foo</div> -->
  <!-- 子のCatCardList.vueで「data-testid="cat-list"」としている。 -->
  <div v-if="!pending && data" class="content">
    <cat-card-list :cat-data-list="data" />
  </div>
</template>

<style scoped>
.content {
  margin: auto;
}
</style>
