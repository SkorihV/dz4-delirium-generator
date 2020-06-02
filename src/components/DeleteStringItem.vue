<template>
  <div>
    <button @click="deleteString" :indexBtn="indexDelete">Удалить строчку</button>
  </div>
</template>

<script>
export default {
  methods: {
    deleteString() {
      this.$emit("deleteString", this.indexDelete);
    }
  },
  props: {
    indexDelete: Number
  }
};
</script>
