<template>
  <div id="app" class="container mt-5">
    <h1>IDShop</h1>
    <p class="animated fadeInLeft">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Sunt ab dolorum minima doloremque perspiciatis culpa officia eum sit officiis asperiores! Ab facilis aspernatur minima enim corporis assumenda, quod nisi eaque.</p>
    <font-awesome-icon icon="shopping-cart"></font-awesome-icon>
    <price :value="4.23"></price>
  </div>
</template>

<script>
import {FontAwesomeIcon} from "@fortawesome/vue-fontawesome";
import Price from "./components/Price.vue"

export default {
  name: "App",
  components: {
    FontAwesomeIcon,
    Price
  },
};
</script>

