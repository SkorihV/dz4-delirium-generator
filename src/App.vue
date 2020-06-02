<template>
  <div id="app">
    <div class="wrapper">
      <app-string-arr :stringForShow="stringForShow"></app-string-arr>
      <app-btn-add @add="generateString"></app-btn-add>
    </div>
  </div>
</template>

<script>
import BtnAddElem from "./components/BtnAddElem.vue";
import StringArr from "./components/StringsArr.vue";

export default {
  name: "App",
  data: () => ({
    stringForShow: "",
    objArr: {
      arrWhen: [
        "Завтра",
        "Сегодня",
        "После дождика в четверг",
        "Никогда",
        "Йогурт"
      ],
      arrWho: [
        "Я",
        "Илон Маск",
        "Микки Маус",
        "Колобок",
        "Петросян",
        "Селезень"
      ],
      arrThen: [
        "хорошо",
        "быстро",
        "медленно",
        "странно",
        "красиво",
        "интересно"
      ],
      arrWhatDid: [
        "съел",
        "испортил",
        "погулял",
        "отобрал",
        "уехал",
        "исправил",
        "мартышка",
        "помыл"
      ],
      arrWhat: ["яблоко", "торт", "доп работу", "посуду", "деньги"]
    }
  }),
  methods: {
    generateString() {
      const mass = Object.entries(this.objArr);
      const massString = [];
      mass.forEach(item => {
        const randomNum = Math.floor(Math.random() * item[1].length);
        massString.push(item[1][randomNum]);
      });
      this.stringForShow = massString.join(" ");
    }
  },
  components: {
    appBtnAdd: BtnAddElem,
    appStringArr: StringArr
  }
};
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  border: antiquewhite 1px solid;
  width: 50%;
}
</style>
