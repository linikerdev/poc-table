<template>
  <vue-good-table
    ref="MyCoolTable"
    :columns="columns"
    :rows="rows"
    :group-options="{
  	  enabled: true,
      collapsable: true
    }"
  ></vue-good-table>
</template>

<script>
export default {
  data: function() {
    return {
      columns: [
        {
          label: "Name",
          field: "name"
        },
        {
          label: "Age",
          field: "age",
          type: "number"
        },
        {
          label: "Percent",
          field: "score",
          type: "percentage"
        }
      ],
      rows: [
        {
          id: 0,
          name: "Senior Devs",
          age: 20,
          score: 0.15296,
          children: [
            { id: 1, name: "John", age: 20, score: 0.03845 },
            { id: 2, name: "Jane", age: 24, score: 0.02948 },
            { id: 3, name: "Susan", age: 16, score: 0.08503 }
          ]
        },
        {
          id: 4,
          name: "Junior Devs",
          score: 0.12069,
          children: [
            { id: 5, name: "Chris", age: 55, score: 0.02946 },
            { id: 6, name: "Dan", age: 40, score: 0.09123 }
          ]
        }
      ]
    };
  }
};
</script>

<style >
#app {
  padding: 20px;
  font-family: sans-serif;
}
.button-group {
  margin-bottom: 20px;
  text-align: right;
}
</style>