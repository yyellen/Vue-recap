<template>
  <div class="wrapper">
		<h2>use component</h2>
		<div style="padding-bottom :20px">
			<input type="text" v-model="name">
			<input type="number" v-model="price">
			<button @click="newItem">add</button>
		</div>
		<div class="product-list">
			<!-- 沒冒號丟字串，通常是丟變數 -->
			<!-- <productItem name="Flash"></productItem>-->
			<!-- 有冒號丟變數，設定很多變數時會分行  -->
			<productItem 
			v-for="product in products" :key="product.id"
			:name="product.name"
			:price="product.price"></productItem> 
		</div>

		<h2>no component</h2>
    <div class="product-list">
      <div class="product-item" v-for="product in products" v-bind:key="product.id">
        <h3>{{ product.name }}</h3>
        ${{ product.price }}
      </div>
    </div>
  </div>
</template>

<script>
import ProductItem from "@/components/ProductItem"

export default {
  name: "ProductsView",
	components: {
		ProductItem
	},
  data() {
    return {
			name:"",
			price: 0,
      products: [
        {
          id: 1,
          name: "Spiderman",
          price: 100,
        },
        {
          id: 2,
          name: "Superman",
          price: 200,
        },
        {
          id: 3,
          name: "Ironman",
          price: 300,
        },
        {
          id: 4,
          name: "Batman",
          price: 400,
        },
      ],
    };
  },
	methods: {
		newItem(){
			let name=this.name;
			let price=this.price;

			this.products.push({
				id: 5,
				name: name,
				price: price
			})
		}
	}
};
</script>

<style>
.product-list {
  display: flex;
  flex-wrap: wrap;
}

.product-item {
	/* width: 25%; */
	/* 一排塞四個扣掉margin */
  width: calc(25% - 10px); 
  margin: 0 5px 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-shadow: 0 2px 5px #aaa;
  padding: 10px;
}
</style>