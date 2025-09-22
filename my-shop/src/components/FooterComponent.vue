<template>
  <footer class="footer">
    <div class="footer-content">
      <!-- Контактна інформація -->
      <div class="footer-contacts">
        <h3>Контакти</h3>
        <p>Email: <a href="mailto:info@shop.com">info@shop.com</a></p>
        <p>Телефон: <a href="tel:+380123456789">+38 (012) 345-67-89</a></p>
      </div>

      <!-- Список посилань -->
      <div class="footer-links">
        <h3>Інформація</h3>
        <ul>
          <li><a href="/about">Про нас</a></li>
          <li><a href="/delivery">Доставка</a></li>
        </ul>
      </div>
    </div>

    <div class="footer-bottom">
      <p>© 2025 MyShop. Усі права захищені.</p>
    </div>
  </footer>
</template>

<script>
export default {
  name: "FooterComponent",
};
</script>

<style scoped>
.footer {
  background-color: #2c3e50; /* темний фон, як у шапці */
  color: #ecf0f1; /* світлий текст */
  padding: 20px 40px;
  margin-top: 40px;
}

.footer-content {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 30px;
}

.footer h3 {
  margin-bottom: 10px;
  font-size: 1.2rem;
  color: #f39c12; /* акцентний колір, як у кнопок/карток */
}

.footer a {
  color: #ecf0f1;
  text-decoration: none;
  transition: color 0.3s;
}

.footer a:hover {
  color: #f39c12;
}

.footer-bottom {
  text-align: center;
  margin-top: 20px;
  border-top: 1px solid rgba(255, 255, 255, 0.2);
  padding-top: 10px;
  font-size: 0.9rem;
}
</style>
