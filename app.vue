<script setup lang="ts">
import type { Lottery } from "~/model/lottery";


useState<Map<number, Lottery>>(
  "lotteryCollection",
  () => new Map<number, Lottery>()
);
</script>

<template>
  <NuxtPage />
</template>
