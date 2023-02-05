<script lang="ts" setup>
import { CatResponse } from "~~/types/idnex";

// 受け取るものの型を宣言
interface Props {
  catData: CatResponse;
}

// Propsという変数で親から受け取る。
defineProps<Props>();
</script>

<template>
  <div>
    <img
      class="card-img"
      :src="catData.url"
      alt="cute cat"
      :data-testid="catData.id"
    />
  </div>
</template>

<style scoped>
.card-img {
  border-radius: 8px;
  width: 320px;
  height: 320px;
  object-fit: cover;
}
</style>
