<template>
  <ag-grid-vue
    style="width: 90%; height: 500px"
    class="ag-theme-alpine"
    :column-defs="columnDefs"
    :row-data="rowData"
    :enable-charts="true"
    :enable-range-selection="true"
  >
  </ag-grid-vue>
</template>

<script lang="ts">
  import { ColDef } from 'ag-grid-community'
  import 'ag-grid-community/styles/ag-grid.css'
  import 'ag-grid-community/styles/ag-theme-alpine.css'
  import 'ag-grid-enterprise'
  import { AgGridVue } from 'ag-grid-vue3'

  export default {
    name: 'App',
    components: {
      AgGridVue,
    },
    setup() {
      const colDefs: ColDef[] = [
        { headerName: 'Make', field: 'make' },
        { headerName: 'Model', field: 'model' },
        { headerName: 'Price', field: 'price' },
      ]

      return {
        columnDefs: colDefs,
        rowData: [
          { make: 'Toyota', model: 'Celica', price: 35000 },
          { make: 'Ford', model: 'Mondeo', price: 32000 },
          { make: 'Porsche', model: 'Boxster', price: 72000 },
        ],
      }
    },
  }
</script>

<style scoped>
  a {
    color: #42b983;
  }

  label {
    margin: 0 0.5em;
    font-weight: bold;
  }

  code {
    background-color: #eee;
    padding: 2px 4px;
    border-radius: 4px;
    color: #304455;
  }
</style>
