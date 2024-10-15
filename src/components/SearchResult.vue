<template>
  <div :class="`py-10 ${isFirst ? '' : 'border-t border-gray-200'}`">
    <div>
        <SearchedTextDisplay :text="this.item.title" :searchString="searchString" :class="'text-2xl font-semibold'"></SearchedTextDisplay>
    </div>
    <div class="italic pb-2">
        {{ new Date(this.item.epoch).toLocaleDateString('en-US', { year: 'numeric', month: 'short', day: '2-digit' }) }}
    </div>
    <div>
        <SearchedTextDisplay :text="this.item.article" :searchString="searchString"></SearchedTextDisplay>
    </div>
  </div>
</template>

<script>
import SearchedTextDisplay from "./SearchedTextDisplay.vue";

export default {
  name: "SearchResults",
  props: {
    isFirst: Boolean,
    searchString: String,
    item: Object,
  },
  components: {
    SearchedTextDisplay,
  },
};
</script>
