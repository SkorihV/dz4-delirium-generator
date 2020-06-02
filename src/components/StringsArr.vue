<template>
  <div class="stringItemsList">
    <div class="stringItem" v-for="(item, index) in stringList" :key="index">{{item}}</div>
  </div>
</template>

<script>
export default {
  data: () => ({
    stringList: []
  }),
  props: {
    stringForShow: String
  },
  watch: {
    stringForShow() {
      this.stringList.push(this.stringForShow);
    }
  }
};
</script>

<style scoped>
.stringItem {
  padding: 10px;
  margin: 5px;
  border-right: 2px solid green;
}
.stringItemsList {
  flex-grow: 1;
}
</style>
