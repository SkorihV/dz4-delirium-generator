<template>
  <div class="stringItemsList">
    <div class="stringItem" v-for="(item, index) in stringList" :key="index">
      <div>{{ item }}</div>
      <span><delete @deleteString="deleteItem(index)" :indexDelete="index"></delete></span>
    </div>
  </div>
</template>

<script>
import DeleteString from "./DeleteStringItem.vue";

export default {
  data: () => ({
    stringList: []
  }),
  methods: {
    deleteItem(index) {
      this.stringList.splice(index, 1);
    }
  },
  props: {
    stringForShow: String
  },
  watch: {
    stringForShow() {
      this.stringList.push(this.stringForShow);
    }
  },
  components: {
    delete: DeleteString
  }
};
</script>

<style scoped>
.stringItem {
  padding: 10px;
  margin: 5px;
  border-right: 2px solid green;
  display: flex;
  justify-content: space-between;
}
.stringItemsList {
  flex-grow: 1;
}
</style>
