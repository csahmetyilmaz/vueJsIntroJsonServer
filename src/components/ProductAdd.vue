<template>
  <div id="addForm">
    <button class="btn btn-primary">Add new product</button>
    <form @submit.prevent="handleAdd">
      <div class="form-group">
        <label for="categoryId">CategoryId</label>
        <input
          v-model="product.categoryId"
          class="form-control"
          id="categoryId"
        />
      </div>
      <div class="form-group">
        <label for="productName">Product</label>
        <input
          v-model="product.productName"
          class="form-control"
          id="productName"
        />
      </div>
      <div class="form-group">
        <label for="quantityPerUnit">Quantity / Unit</label>
        <input
          v-model="product.quantityPerUnit"
          class="form-control"
          id="quantityPerUnit"
        />
      </div>
      <div class="form-group">
        <label for="unitPrice">Price/u</label>
        <input
          v-model="product.unitPrice"
          class="form-control"
          id="unitPrice"
        />
      </div>
      <div class="form-group">
        <label for="unitInStock">Stock</label>
        <input
          v-model="product.unitInStock"
          class="form-control"
          id="unitInStock"
        />
      </div>
      <button type="submit" class="btn btn-sm btn-success m-1">Add</button>
    </form>
  </div>
</template>
<script>
export default {
  name: "product-add",
  data() {
    return {
      product: {
        categoryId: "",
        productName: "",
        quantityPerUnit: "",
        unitPrice: "",
        unitInStock: "",
      },
    };
  },
  props: {
    products: Array,
  },
  methods: {
    handleAdd() {
      this.$emit("add:product", this.product);
    },
  },
};
</script>
<style scoped>
#addForm {
  margin: 30px;
}
</style>