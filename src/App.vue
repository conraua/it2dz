<template>
  <div id="app">
    <div class="row">
      <div id="input" class="col-md-12">
        <div class="row">
          <div class="col-md-4">
          </div>
          <div class="col-md-4">
            <input v-model.trim="inputSearch" type="text" placeholder="Поиск по названию товара">
          </div>
          <div class="col-md-4">
          </div>
        </div>
      </div>
    </div>
    <div class="row">
      <div id="card" is="Cardholder" v-for="product in filteredProducts" :product="product" :key="product.id"></div>
    </div>
  </div>
</template>

<script>
import Cardholder from './components/Cardholder.vue'
export default {
  name: 'app',
  components: {
    Cardholder,
  },
  data: function() {
    return {
      inputSearch: "",
      products: [
        {
          id: 1,
          name: "Juice",
          image: "1.jpeg",
          description: "Вкуснейший сок",
          price: 100,
        },
        {
          id: 2,
          name: "Snacks",
          image: "2.jpeg",
          description: "Чипсы из активированного угля",
          price: 95,
        },
        {
          id: 3,
          name: "Laptop",
          image: "3.jpg",
          description: "Ноутбук игровой. 2 ядра + 2 гига",
          price: 50000,
        },
        {
          id: 4,
          name: "IPhone",
          image: "4.jpeg",
          description: "3(!) камеры",
          price: 999999,
        },
        {
          id: 5,
          name: "Jeans",
          image: "5.jpeg",
          description: "Джинсы Виктора Цоя",
          price: 10000,
        },
        {
          id: 6,
          name: "Sneakers",
          image: "6.jpg",
          description: "Кроссовки, снятые с Тупака",
          price: 24000,
        },
        {
          id: 7,
          name: "Watch",
          image: "7.jpg",
          description: "Часы наручные с кукушкой",
          price: 100500,
        },
        {
          id: 8,
          name: "Chewing Gum",
          image: "8.jpg",
          description: "Жвачка 'Комплексный обед'",
          price: 1,
        }
      ]
    }
  },
  computed: {
    filteredProducts: function() {
      var that = this;
      return this.products.filter(function(product) {
          return ((product.name.toLowerCase().indexOf(that.inputSearch.toLowerCase()) !== -1) ||
           (product.description.toLowerCase().indexOf(that.inputSearch.toLowerCase()) !== -1));
      }); 
    } 
  }
}
</script>

<style>
#app {

}

#card {
  border-style: groove;
  border-width: 1;
  border-color: blue;
}

#input {
  margin-bottom: 3%;
}
</style>
