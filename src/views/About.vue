<template>
  <div class="home">
    <user/>
    
    <table class="table">
      <thead class="thead-dark">
        <tr>
          <th scope="col">ชื่อสินค้า</th>
          <th scope="col">ราคา</th>
          <th scope="col">จำนวน</th>
          <th scope="col">รวม</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(mi, index) in select" :key="index">
          <td>{{ mi.NameProduct }}</td>
          <td>{{ mi.Price }}</td>
          <td>{{ mi.Amount }}</td>
          <td>{{ mi.Total }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
// @ is an alias to /src
import { mapState } from "vuex";
import User from "../components/User.vue";

export default {
  name: "Home",
  components: {
    User
  },
  computed: {
    ...mapState(["select"]),
  },
};
</script>
