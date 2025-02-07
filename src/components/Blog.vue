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
    this.blockMap = await getPageBlocks("19375c89bc778031b015dc2ef9d2aa40");
  },
};
</script>

<style>
/* optional Notion-like styles */
@import "vue-notion/src/styles.css";
</style>
