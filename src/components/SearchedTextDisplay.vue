<template>
    <span>
      <span v-for="(item, key) in this.splitString"  :key="key" :class="item.toLowerCase() === this.searchString.toLowerCase() ? 'bg-yellow-200' : ''">{{ item }}</span>
    </span>
  </template>
  
  <script>
  export default {
    name: "SearchedTextDisplay",
    props: {
      text: String,
      searchString: String
    },
    computed: {
      splitString() {
        let startIndex = 0;
        let subStringsArr = []
        let string = this.text
        if(!this.searchString){
            return [string]
        }
        while ((startIndex = string.toLowerCase().indexOf(this.searchString.toLowerCase())) !== -1) {
            subStringsArr.push(string.slice(0, startIndex))
            subStringsArr.push(string.slice(startIndex, startIndex + this.searchString.length))
            string = string.slice(startIndex + this.searchString.length)
        }
        subStringsArr.push(string)
        return subStringsArr
      }
    }
  };
  </script>