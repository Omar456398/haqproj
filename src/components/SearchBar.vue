<template>
  <div class="mb-8 mx-3">
    <div class="my-10 text-4xl">Search</div>
    <input
      type="text"
      placeholder="Search"
      class="w-full p-3 text-xl border rounded-lg focus:outline-none"
      @input="updateSearchEmit"
      v-model="searchText"
    />
    <p class="mt-4"><b>{{numberOfPosts}} {{ postPosts }}</b> {{ wasWere }} found.</p>
  </div>
</template>

<script>
export default {
  name: "SearchBar",
  emits: ['updateSearchEmit'],
  props: {
    numberOfPosts: Number
  },
  data: () => ({
    searchQuery: '',
  }),
  computed: {
    postPosts() {
        return this.numberOfPosts === 1 ? 'post' : 'posts'
    },
    wasWere() {
        return this.numberOfPosts === 1 ? 'was' : 'were'
    }
  },
  methods: {
    updateSearchEmit() {
        this.$emit('updateSearchEmit', this.searchText);
    }
  }
};
</script>