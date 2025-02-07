<template>
  <NotionRenderer :blockMap="blockMap" fullPage />
</template>

<script lang="ts">
import { NotionRenderer, getPageBlocks } from "vue-notion";

export default {
  components: { NotionRenderer },
  data: () => ({ blockMap: null }),
  async created() {
    // get Notion blocks from the API via a Notion pageId
    this.blockMap = await getPageBlocks("19375c89bc7780f4bc3ce68b2653f414");
  },
};
</script>

<style>
/* optional Notion-like styles */
@import "vue-notion/src/styles.css";
</style>
