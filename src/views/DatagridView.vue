<template>
  <div>
    <ag-grid-vue
      domLayout="autoHeight"
      :rowData="rowData"
      :columnDefs="columnDefs"
      :theme="theme"
    />
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import { ModuleRegistry, AllCommunityModule, themeQuartz } from 'ag-grid-community'
import { AgGridVue } from 'ag-grid-vue3'
ModuleRegistry.registerModules([AllCommunityModule])

const theme = ref(
  themeQuartz.withParams({
    backgroundColor: 'rgb(249, 245, 227)',
    foregroundColor: 'rgb(126, 46, 132)',
    headerTextColor: 'rgb(204, 245, 172)',
    headerBackgroundColor: 'rgb(209, 64, 129)',
    oddRowBackgroundColor: 'rgb(0, 0, 0, 0.03)',
    headerColumnResizeHandleColor: 'rgb(126, 46, 132)',
  }),
)

const columnDefs = ref([
  { field: 'make', headerName: 'Make' },
  { field: 'model', headerName: 'Model' },
  { field: 'price', headerName: 'Price' },
])

const rowData = ref([
  { make: 'Toyota', model: 'Celica', price: 35000 },
  { make: 'Ford', model: 'Mondeo', price: 32000 },
  { make: 'Porsche', model: 'Boxster', price: 72000 },
  { make: 'Porsche', model: '911', price: 122000 },
])
</script>
