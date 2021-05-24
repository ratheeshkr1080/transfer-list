<template>
  <div class="autocomplete">
    <input
      v-model="search"
      :placeholder="placeholder"
      @input="onChange"
      @click="onChange"
      type="text"
    />
    <div v-if="results && isOpen">
      <ul>
        <li
          v-for="(result, i) in results"
          :key="i"
          @click="setResult(result)"
          class="autocomplete-result"
        >
          {{ result }}
        </li>
      </ul>
    </div>
  </div>
</template>
 
<script>
export default {
  name: 'AutoComplete',
  props: {
    items: {
      type: [String, Function, Array, Object],
      required: false,
      default: () => [],
    },
    placeholder :{
      default : 'Search'
    }
    
  },
  data() {
    return {
      search: '',
      results: [],
      isOpen: false,
    };
  },
  methods: {
    filterResults() {
      this.results = this.items.filter(item => item.toLowerCase().indexOf(this.search.toLowerCase()) > -1);
    },
    onChange() {
      this.filterResults();
      this.isOpen = true;
    },
    setResult(result) {
      this.search = result;
      this.isOpen = false;
    },
    handleClickOutside(event) {
      if (!this.$el.contains(event.target)) {
        this.isOpen = false;
      }
    }
  },
  mounted() {
    document.addEventListener('click', this.handleClickOutside);
  },
  destroyed() {
    document.removeEventListener('click', this.handleClickOutside);
  }
}
</script>
<style>
  .autocomplete {
    position: relative;
  }
 
  .autocomplete-results {
    padding: 0;
    margin: 0;
    border: 1px solid #eeeeee;
    height: 120px;
    min-height: 1em;
    max-height: 6em;
    overflow: auto;
  }
 
  .autocomplete-result {
    list-style: none;
    text-align: left;
    padding: 4px 2px;
    cursor: pointer;
  }
 
  .autocomplete-result:hover {
    background-color: #4AAE9B;
    color: white;
  }
</style>