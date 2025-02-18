<template>
  <div>
    <h2>Пошук товарів</h2>
    <input
      v-model="searchQuery"
      placeholder="Введіть назву товару"
    />
    <ProductList :products="filteredProducts" />
  </div>
</template>

<script>
import ProductList from '../components/ProductList.vue';

export default {
  components: {
    ProductList,
  },
  data() {
return {
  searchQuery: "", // Що шукає користувач
products: [
{
name: "Смартфон Samsung Galaxy S23",
price: 35000,
image: "https://img.freepik.com/free-photo/white-cell-phone-box-background_58702-4721.jpg"
},
{
name: "Ноутбук Apple MacBook Air M2",
price: 58000,
image: "https://img.freepik.com/free-photo/workplace-with-laptop-stand-near-eyeglasses_23-2148040478.jpg"
},
{
name: "Бездротові навушники Sony",
price: 7800,
image: "https://img.freepik.com/free-photo/closeup-shot-white-wireless-headphones-with-their-case-white-background_181624-31412.jpg"
},
{
name: "Механічна клавіатура HyperX",
price: 4500,
image: "https://img.freepik.com/free-photo/top-view-keyboard-mouse-arrangement_23-2149386333.jpg"
},
{
name: "Смарт-годинник Apple Watch Series 9",
price: 17000,
image: "https://img.freepik.com/free-photo/modern-sport-adult-hand-lifestyle_1127-2745.jpg"
},
{
name: "Портативна колонка JBL Series 1",
price: 5200,
image: "https://img.freepik.com/free-photo/still-life-tech-device_23-2150722602.jpg"
},
{
name: "Телевізор Samsung 4K QLED",
price: 28000,
image: "https://img.freepik.com/free-photo/landscape-nature-scene-tv-appliance-generative-ai_188544-12122.jpg"
},
{
name: "Фітнес-браслет Xiaomi Mi Band 7",
price: 1800,
image: "https://img.freepik.com/free-photo/futuristic-virtual-reality-headset-illuminates-dark-studio-shot-generated-by-ai_188544-13298.jpg"
}
],
};
},
computed: {
    filteredProducts: function () {
        // Фільтруємо список товарів на основі тексту пошуку
        return this.products.filter(function (product) {
            return product.name.toLowerCase().includes(this.searchQuery.toLowerCase());
        }.bind(this));
    }
},

};
</script>
<!-- Приклад домашнього завдання -->
<style scoped>
input {
  width: 100%; /* Займає всю ширину контейнера */
  max-width: 600px; /* Обмеження ширини */
  margin: 0 auto 20px; /* Центрування і відступ знизу */
  padding: 10px 15px; /* Відступи всередині інпуту */
  font-size: 16px; /* Розмір тексту */
  border: 1px solid #ccc; /* Світло-сіра рамка */
  border-radius: 25px; /* Закруглені кути */
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1); /* Легка тінь */
  transition: all 0.3s ease; /* Анімація змін кольору */
}
input:focus {
  outline: none; /* Забирає стандартну синю рамку браузера */
  border: 1px solid #007bff; /* Синя рамка */
  box-shadow: 0 3px 8px rgba(0, 123, 255, 0.4); /* Яскравіша тінь */
}
h2 {
  text-align: center; /* Текст по центру */
  margin-bottom: 20px; /* Відступ знизу */
}
</style>

