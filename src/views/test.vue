<script>
import xlsx from 'xlsx/dist/xlsx.full.min'

function exportTableToExce(tableElement, filename) {
  const table = document.querySelector(tableElement)
  const tableData = []

  // Extract table data
  table.querySelectorAll('tr').forEach((row) => {
    const rowData = []
    row.querySelectorAll('th, td, input').forEach((cell) => {
      rowData.push(cell.textContent)
    })
    tableData.push(rowData)
  })

  // Create worksheet
  const worksheet = xlsx.utils.aoa_to_sheet(tableData)

  // Create workbook
  const workbook = xlsx.utils.book_new()
  xlsx.utils.book_append_sheet(workbook, worksheet, 'Sheet1')

  // Export the workbook to Excel file
  xlsx.writeFile(workbook, filename)
}
</script>

<template>
  <table ref="exportable_table">
    <tbody>
      <tr>
        <td>1</td>
        <td><input type="text" placeholder="Nhập dữ liệu" /></td>
        <td><input type="number" placeholder="Nhập dữ liệu" /></td>
        <td><input type="number" placeholder="Nhập dữ liệu" /></td>
        <td><input type="text" placeholder="Nhập dữ liệu" /></td>
      </tr>
      <tr>
        <td>Row 2 - Column 1</td>
        <td>Row 2 - Column 2</td>
        <td>Row 2 - Column 3</td>
      </tr>
      <tr>
        <td>Row 3 - Column 1</td>
        <td>Row 3 - Column 2</td>
        <td>Row 3 - Column 3</td>
      </tr>
    </tbody>
  </table>
  <input type="text" v-model="name" />
  <button @click="exportTableToExcel()">Export table to excel xls</button>
</template>
