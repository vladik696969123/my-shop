<template>
  <div>
    <h2>Додати новий товар</h2>
    <form v-on:submit.prevent="addProduct">
      <input
        type="text"
        v-model="newProduct.name"
        placeholder="Назва товару"
        required
      />
      <textarea
        v-model="newProduct.description"
        placeholder="Опис товару"
        required
      ></textarea>
      <input
        type="number"
        v-model.number="newProduct.price"
        placeholder="Ціна (грн):"
        required
      />
      <input
        type="text"
        v-model="newProduct.image"
        placeholder="Посилання на зображення:"
        required
      />
      <button type="submit">Додати товар</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newProduct: {
        name: "",
        description: "",
        price: null,
        image: "",
      },
      nextId: 9, // Початкова кількість ID
    };
  },
  methods: {
    addProduct() {
    const product = {
        id: this.nextId++, // Генеруємо унікальний ID
        ...this.newProduct,
      };

      this.$emit("add-product", product); // Передаємо новий товар у батьківський компонент

      // Очищаємо форму
      this.newProduct = {
        name: "",
        description: "",
        price: null,
        image: "",
      };
    },
  },
};
</script>
