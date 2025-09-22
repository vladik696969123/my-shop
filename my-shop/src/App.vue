<template>
  <div id="app">
    <ProductList
    name="Українська вишиванка"
    description="Стильна вишиванка з традиційними орнаментами."
    price="1500"
    image="https://content1.rozetka.com.ua/goods/images/big/383454333.jpg"/>
    <FooterComponent />
  </div>
</template>

<script>
import ProductList from './components/ProductList.vue';
import FooterComponent from './components/FooterComponent.vue';

export default{
  components:{
    ProductList,
    FooterComponent
  }
};
</script>