<template>
  <div class="admin-panel">
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
      if (
        !this.newProduct.name ||
        !this.newProduct.price ||
        !this.newProduct.image
      ) {
        alert("Будь ласка, заповніть всі поля!");
        return;
      }

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
