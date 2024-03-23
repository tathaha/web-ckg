<template>
  <div class="wrapper-dgxl">
    <div ref="dgxl" class="grid"></div>
    <input type="button" value="Add new row" @click="dgxlObj.insertEmptyRows()" />
    <input type="button" value="Download data as CSV" @click="dgxlObj.downloadDataAsCSV()" /><br />
  </div>
</template>

<script>
import DataGridXL from '@datagridxl/datagridxl2'

export default {
  name: 'DataGrid',
  data() {
    return {}
  },
  computed: {
    dgxlOptions() {
      return {}
    }
  },
  mounted: function () {
    const dgxlObj = new DataGridXL(this.$refs.dgxl, this.dgxlOptions)
    Object.assign(this, { dgxlObj }) // tucks all methods under dgxlObj object in component instance
  }
}
</script>

<style>
.grid {
  height: 400px;
}
</style>
