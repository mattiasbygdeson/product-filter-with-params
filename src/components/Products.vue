<template>
  <div>
    <h2>{{listTitle}}</h2>

    <SingleProduct v-for="product in products" :key="product.id" :productInfo="product" />
  </div>
</template>

<script>
import SingleProduct from "./SingleProduct";

export default {
  name: "Products",
  components: {
    SingleProduct
  },
  data() {
    return {
      listTitle: "",
      products: [
        { id: 1 },
        { id: 2 },
        { id: 3 },
        { id: 4 },
        { id: 5 },
        { id: 6 },
        { id: 7 },
        { id: 8 },
        { id: 9 }
      ]
    };
  },
  mounted() {
    this.listTitle = "Product list";
    this.generateList();
  },
  methods: {
    generateList() {
      /**
       * Get the uri string of product ids and hash it up
       * First index will be the list title
       * Loop through all remaining indexes
       *
       * URI string model:
       * http://localhost:8080/products/name-separated-with-dashes:2000:2130:1310:8290
       *
       */

      if (this.$route.params.favlist) {
        //eslint-disable-next-line no-console
        console.log("There are some params, let's run the function!");

        // Hash string up into array
        var idString = this.$route.params.favlist;
        var idArray = idString.split(":");

        // Set the title
        var newTitle = idArray[0].replace(/-/g, " ");
        var newTitleCapitalized =
          newTitle.charAt(0).toUpperCase() + newTitle.slice(1);
        this.listTitle = newTitleCapitalized;

        // Delete first index, array will now only contain IDs
        idArray.shift();

        // Set the products
        this.products = [];

        for (var i = 0; idArray.length > i; i++) {
          var newProduct = { id: idArray[i] };
          this.products = [...this.products, newProduct];
        }
      }
    }
  }
};
</script>
