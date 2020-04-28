<template>
  <div>
    <h2>teste 222</h2>
  </div>
  <!-- <b-card>
    <b-row class="mb-2">
      <b-col sm="3" class="text-sm-right"><b>Age:</b></b-col>
      <b-col>{{ row.item.age }}</b-col>
    </b-row>

    <b-row class="mb-2">
      <b-col sm="3" class="text-sm-right"><b>Is Active:</b></b-col>
      <b-col>{{ row.item.isActive }}</b-col>
    </b-row>

    <b-button size="sm" @click="row.toggleDetails">Hide Details</b-button>
  </b-card> -->
</template>

<script>
export default {
  name: "collapse_table",
  props: {
    row: {
      type: Object,
    },
  },
};
</script>

<style></style>
