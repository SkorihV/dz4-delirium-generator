<template>
  <div class="btnWrapper">
    <button @click="add">Добавить бреда</button>
  </div>
</template>


<script>
export default {
  methods: {
    add() {
      this.$emit("add");
    }
  }
};
</script>

<style scoped>
button {
  height: 50px;
  padding: 20px;
  display: flex;
  align-items: center;
  background: aquamarine;
  cursor: pointer;
}

button:hover {
  background: red;
  color: white;
}

.btnWrapper {
  margin: 20px;
}
</style>
