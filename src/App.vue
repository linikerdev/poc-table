<template>
  <vue-good-table
    styleClass="vgt-table condensed"
    :expandedOptions="{
      key: 'ranking',
      expandedRows,
      styleClass: 'my-custom-class'
    }"
    :rows="rows"
    :columns="columns"
  >
    <template slot="expanded-row" slot-scope="props">
      <div class="rowCollapse">
        <!-- <span>posso incluir qualquer coisa <strong>{{props.row.name}}</strong></span> -->

        <b-table class="tableCollapse" hover :items="props.row.child"></b-table>
      </div>
    </template>
    <template slot="table-row" slot-scope="props">
      <span v-if="props.column.field == 'icon'">
        <span @click="clicked(props.row.ranking)" class="iconClick">
          <b-icon-chevron-up v-if="parseInt(expandedRows) === parseInt(props.row.ranking)" />
          <b-icon-chevron-down v-else />
        </span>
      </span>
      <span v-else>{{props.formattedRow[props.column.field]}}</span>
    </template>
  </vue-good-table>
</template>

<script>
export default {
  data() {
    return {
      expandedRows: [1],
      columns: [
        { sortable: false, width: "30%", label: "Name", field: "name" },
        { sortable: false, width: "30%", label: "BIB", field: "BIB" },
        { sortable: false, width: "30%", label: "NOC", field: "NOC" },
        { sortable: false, width: "10%", label: "", field: "icon" }
      ],
      rows: [
        {
          ranking: 0,
          BIB: 36,
          name: "Oliver Macdonald",
          gender: "male",
          NOC: "OTHERWAY",
          child: [
            {
              vault: 3.2222,
              unevenbars: 4.2222,
              beam: 6.333,
              floor: 5.444,
              total: 19.22233
            },
            {
              vault: 3.2222,
              unevenbars: 4.2222,
              beam: 6.333,
              floor: 5.444,
              total: 19.22233
            },
            {
              vault: 3.2222,
              unevenbars: 4.2222,
              beam: 6.333,
              floor: 5.444,
              total: 19.22233
            },
            {
              vault: 3.2222,
              unevenbars: 4.2222,
              beam: 6.333,
              floor: 5.444,
              total: 19.22233
            }
          ]
        },
        {
          ranking: 1,
          BIB: 26,
          name: "Roach Chang",
          gender: "male",
          NOC: "MENBRAIN",
          child: [
            {
              vault: 3.2222,
              unevenbars: 4.2222,
              beam: 6.333,
              floor: 5.444,
              total: 19.22233
            },
            {
              vault: 3.2222,
              unevenbars: 4.2222,
              beam: 6.333,
              floor: 5.444,
              total: 19.22233
            },
            {
              vault: 3.2222,
              unevenbars: 4.2222,
              beam: 6.333,
              floor: 5.444,
              total: 19.22233
            },
            {
              vault: 3.2222,
              unevenbars: 4.2222,
              beam: 6.333,
              floor: 5.444,
              total: 19.22233
            }
          ]
        },
        {
          ranking: 2,
          BIB: 20,
          name: "Lillian Abbott",
          gender: "female",
          NOC: "OVIUM",
          child: [
            {
              vault: 3.2222,
              unevenbars: 4.2222,
              beam: 6.333,
              floor: 5.444,
              total: 19.22233
            },
            {
              vault: 3.2222,
              unevenbars: 4.2222,
              beam: 6.333,
              floor: 5.444,
              total: 19.22233
            },
            {
              vault: 3.2222,
              unevenbars: 4.2222,
              beam: 6.333,
              floor: 5.444,
              total: 19.22233
            },
            {
              vault: 3.2222,
              unevenbars: 4.2222,
              beam: 6.333,
              floor: 5.444,
              total: 19.22233
            }
          ]
        },
        {
          ranking: 3,
          BIB: 21,
          name: "Heath Odonnell",
          gender: "male",
          NOC: "ESCHOIR",
          child: [
            {
              vault: 3.2222,
              unevenbars: 4.2222,
              beam: 6.333,
              floor: 5.444,
              total: 19.22233
            },
            {
              vault: 3.2222,
              unevenbars: 4.2222,
              beam: 6.333,
              floor: 5.444,
              total: 19.22233
            },
            {
              vault: 3.2222,
              unevenbars: 4.2222,
              beam: 6.333,
              floor: 5.444,
              total: 19.22233
            },
            {
              vault: 3.2222,
              unevenbars: 4.2222,
              beam: 6.333,
              floor: 5.444,
              total: 19.22233
            }
          ]
        }
      ]
    };
  },
  methods: {
    clicked(clickedId) {
      if (this.expandedRows.some(id => id == clickedId)) {
        this.expandedRows = this.expandedRows.filter(v => v !== clickedId);
      } else {
        this.expandedRows.push(clickedId);
      }
    }
  }
};
</script>

<style lang="scss" >
$color_default: #447ac0;
$color_default_dark: #202b5a;

.vgt-table {
  background: none !important;
  border: none !important;

  thead {
    background: #fcfbfb;
    padding-left: 0 !important;
    padding-right: 0 !important;
    padding-bottom: 0 !important;
    padding-top: 0 !important;
    th {
      font-size: 14px;
      font-family: "Open Sans", sans-serif;
      text-align: left;
      text-transform: uppercase;
      font-weight: 300;
      vertical-align: middle;
      background: #fcfbfb !important;
      border-bottom: 1px solid $color_default !important;
      color: $color_default !important;
      padding-left: 5px !important;
      padding-right: 5px !important;
      padding-bottom: 5px !important;
      padding-top: 5px !important;
      &.vgt-left-align {
        padding-left: 5px !important;
        padding-right: 5px !important;
        padding-bottom: 5px !important;
        padding-top: 5px !important;
      }
      &:nth-child(n) {
        text-align: left;
      }
    }
  }
  tbody {
    scrollbar-color: rebeccapurple green !important;
    scrollbar-width: o !important;
    scroll-margin-right: 0;
    scroll-margin-left: 0;
    padding-left: 0;
    padding-right: 0;
    padding-bottom: 0;
    padding-top: 0;

    td {
      font-size: 12px;
      font-weight: 400;
      // color: #006fac;
      text-transform: uppercase;
      text-align: left;
      vertical-align: middle;
      overflow: hidden;
      padding-left: 5px !important;
      padding-right: 5px !important;
      padding-bottom: 4px !important;
      padding-top: 4px !important;
      &.vgt-left-align {
        padding-left: 5px !important;
        padding-right: 5px !important;
        padding-bottom: 4px !important;
        padding-top: 4px !important;
      }
      &:nth-child(n) {
        text-align: left;
      }
    }
  }
}
.rowCollapse thead tr {
}
.rowCollapse {
  background: #FCFBFB !important;
  padding: 20px;
  .tableCollapse {
    th {
      background: #eee !important;
    }
  }
}
tr.my-custom-class {
  background-color: #fcfbfb;
}
.iconClick {
  cursor: pointer;
}
</style>