
<template>
  <div class="wrapper">
    <form id="search">
      Search
      <input name="query" v-model="searchQuery">
    </form>
    <div id="grid-template">
      <div class="table-header-wrapper">
        <table class="table-header">
          <thead>
            <th v-for="(item, key) in columns" :key="key">
              {{ item[Object.keys(item).join("")
              ] }}
              <span
                class="arrow"
                :class="sortOrders[key] > 0 ? 'asc' : 'dsc'"
              ></span>
            </th>
          </thead>
        </table>
      </div>
      <div class="table-body-wrapper">
        <table class="table-body">
          <tbody>
            <tr v-for="entry in dataPerPage">
              <td v-for="key in columns">
                <!-- {{ Object.keys(key).join('') }} -->
                {{entry[Object.keys(key).join('')]}}
              </td>
            </tr>
          </tbody>
        </table>
      </div>
      <div id="page-navigation">
        <button @click="movePages(-1)">Back</button>
        <p>{{startRow / rowsPerPage + 1}} out of {{Math.ceil(filteredData.length / rowsPerPage)}}</p>
        <button @click="movePages(1)">Next</button>
      </div>
      <select v-model="rowsPerPage">
        <option v-for="pageSize in pageSizeMenu" :value="pageSize">{{pageSize}}</option>
      </select>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    data: Array,
    columns: Array
  },
  data() {
    return {
      searchQuery: "",
      sortKey: "",
      sortOrders: {},
      startRow: 0,
      rowsPerPage: 10,
      pageSizeMenu: [10, 20, 50, 100]
    };
  },
  computed: {
    dataPerPage: function() {
      return this.filteredData.filter(
        (item, index) =>
          index >= this.startRow && index < this.startRow + this.rowsPerPage
      );
    },

    filteredData: function() {
      let sortKey = this.sortKey;
      let filterKey = this.searchQuery && this.searchQuery.toLowerCase();
      let order = this.sortOrders[sortKey] || 1;
      let data = this.data;

      if (filterKey) {
        data = data.filter(function(row) {
          return Object.keys(row).some(function(key) {
            return (
              String(row[key])
                .toLowerCase()
                .indexOf(filterKey) > -1
            );
          });
        });
      }

      if (sortKey) {
        data = data.slice().sort(function(a, b) {
          a = a[sortKey];
          b = b[sortKey];
          return (a === b ? 0 : a > b ? 1 : -1) * order;
        });
      }
      return data;
    }
  },
  filters: {
    // capitalize: function(str) {
    //   return str.charAt(0).toUpperCase() + str.slice(1);
    // }
  },
  methods: {
    sortBy: function(key) {
      debugger;
      this.sortKey = key;
      this.sortOrders[key] = this.sortOrders[key] * -1;
    },
    movePages: function(amount) {
      let newStartRow = this.startRow + amount * this.rowsPerPage;
      if (newStartRow >= 0 && newStartRow < this.filteredData.length) {
        this.startRow = newStartRow;
      }
    }
  },
  created() {
    let sortOrders = {};
    this.columns.forEach(function(key) {
      sortOrders[key] = 1;
    });
    this.sortOrders = sortOrders;
  }
};
</script>

<style>
body {
  font-family: Helvetica Neue, Arial, sans-serif;
  font-size: 14px;
  color: #555;
}

table {
  border-spacing: 0;
  width: 100%;
}

th {
  background-color: #008f68;
  color: rgba(255, 255, 255, 0.66);
  cursor: pointer;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

td {
  border-bottom: 1px #008f68 solid;
}

th,
td {
  min-width: 150px;
  padding: 10px 20px;
}

th.active {
  color: #fff;
}

th.active .arrow {
  opacity: 1;
}

.arrow {
  display: inline-block;
  vertical-align: middle;
  width: 0;
  height: 0;
  margin-left: 5px;
  opacity: 0.66;
}

.arrow.asc {
  border-left: 4px solid transparent;
  border-right: 4px solid transparent;
  border-bottom: 4px solid #FAE042;
}

.arrow.dsc {
  border-left: 4px solid transparent;
  border-right: 4px solid transparent;
  border-top: 4px solid #FAE042;
}

#grid-template {
  display: flex;
  display: -webkit-flex;
  flex-direction: column;
  -webkit-flex-direction: column;
  width: 600px;
}
</style>
