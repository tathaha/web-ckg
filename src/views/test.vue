<template>
  <div class="wrapper-dgxl">
    <div ref="dgxl" class="grid"></div>
    <input type="button" class="buttons" value="Add new row" @click="dgxlObj.insertEmptyRows()" />
    <input
      type="button"
      class="buttons"
      value="Download data as CSV"
      @click="dgxlObj.downloadDataAsCSV()"
    /><br />
  </div>
</template>

<script>
import DataGridXL from '@datagridxl/datagridxl2'

export default {
  name: 'DataGrid',
  data() {
    return {
      time: null
    }
  },
  computed: {
    dgxlOptions() {
      return {
        columns: [
          {
            title: 'Nguyên Vật Liệu'
          },
          {
            title: 'Số lượng'
          },
          {
            title: 'Giá cả (VND)'
          },
          {
            title: 'Ghi chú'
          },
          {
            title: 'set time'
          }
        ]
      }
    }
  },
  mounted: function () {
    const dgxlObj = new DataGridXL(this.$refs.dgxl, this.dgxlOptions)
    Object.assign(this, { dgxlObj })

    this.getTimeFromServer()
  },
  methods: {
    getTimeFromServer() {
      fetch('asia.pool.ntp.org') // Replace with the actual time server URL
        .then((response) => response.json())
        .then((data) => {
          this.time = data.time // Assuming the time server returns the time in the "time" field
        })
        .catch((error) => {
          console.error('Error fetching time from server:', error)
        })
    }
  }
}
</script>

<style>
.grid {
  height: 400px;
  width: 95%;
  margin: 0 auto;
  border: solid black 1px;
  border-radius: 10px;
  margin-top: 100px;
}
.buttons {
  margin-top: 10px;
  margin-left: auto;
  margin-bottom: 2rem;
  margin-right: auto;
  display: block;
  height: 60px;
  width: 200px;
  border-radius: 20px;
  background-color: bisque;
}
</style>
