<template>
  <div class="data-table">
    <div v-bind:class="tableClass" class="table">
      <el-table :data="tableData">
        <el-table-column fixed prop="date" label="Date" width="150"></el-table-column>
        <el-table-column prop="name" label="Name" width="120"></el-table-column>
        <el-table-column prop="state" label="State" width="120"></el-table-column>
        <el-table-column prop="city" label="City" width="120"></el-table-column>
        <el-table-column prop="address" label="Address" width="300"></el-table-column>
        <el-table-column prop="zip" label="Zip" width="120"></el-table-column>
        <el-table-column fixed="right" label="Operations" width="120">
          <template slot-scope="scope">
            <el-button @click="handleClick" type="text" size="small">Detail</el-button>
            <el-button type="text" size="small">Edit</el-button>
          </template>
        </el-table-column>
      </el-table>
    </div>
    <div class="pages">
      <pagination :totalCount="totalCount" />
    </div>
  </div>
</template>

<script>
import Pagination from "../Pagination/Pagination.vue";

export default {
  name: "data-table",
  components: {
    Pagination
  },
  props: {
    tableClass: {
      type: "String"
    },
    totalCount: {
      type: "Number"
    }
  }
};
</script>

<style lang="scss">
.data-table {
  .table {
    padding: 0.5em;
    background: white;
  }
}
</style>
