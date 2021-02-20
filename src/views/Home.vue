<template>
  <div class="about">
    <div class="text-danger">
      ****กรุณากดยืนยันเพื่อยืนยันสินค้าที่ท่านเลือก****
    </div>
    <div class="row">
      <product
        v-for="(item, index) in Menuitem"
        :key="index"
        :NameProduct="item.NameProduct"
        :img="item.img"
        :Price="item.Price"
        :id="index"
        @Order="menuorder"
      />
    </div>
    
  </div>
</template>

<script>
// @ is an alias to /src
import { mapState } from "vuex";
import Product from "../components/Product.vue";
export default {
  name: "Home",
  components: {
    Product,
  },
  computed: {
    ...mapState(["Menuitem"]),
  },
};
</script>
