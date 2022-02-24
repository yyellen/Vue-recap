<template>
    <div class="product-item">
        <h3>{{name}}</h3>
        ${{price}}
      </div>
</template>

<script>
export default {
    name: "ProductItem",
		props: ['name', 'price']
}
</script>

<style>
	.product-item {
		/* width: 25%; */
		/* 一排塞四個 扣掉margin */
		width: calc(25% - 10px); 
		margin: 0 5px 10px;
		border: 1px solid #ccc;
		border-radius: 4px;
		box-shadow: 0 2px 5px #aaa;
		padding: 10px;
	}
</style>