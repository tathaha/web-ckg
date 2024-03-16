<template>
  <div>
    <h1></h1>
    <div class="box">
      <div class="box1">
        <table class="table1" id="mytable">
          <th>STT</th>
          <th>Nguyên Vật Liệu</th>
          <th>Số lượng</th>
          <th>Giá cả (VND)</th>
          <tr>
            <td>1</td>
            <td>Gà</td>
            <td><input type="number" placeholder="Nhập dữ liệu" /></td>
            <td><input type="number" placeholder="Nhập dữ liệu" /></td>
          </tr>
          <tr>
            <td>2</td>
            <td>Cám</td>
            <td><input type="number" placeholder="Nhập dữ liệu" /></td>
            <td><input type="number" placeholder="Nhập dữ liệu" /></td>
          </tr>
          <tr>
            <td>3</td>
            <td>Trứng</td>
            <td><input type="number" placeholder="Nhập dữ liệu" /></td>
            <td><input type="number" placeholder="Nhập dữ liệu" /></td>
          </tr>
          <tr>
            <td>4</td>
            <td>Công Nhân</td>
            <td><input type="number" placeholder="Nhập dữ liệu" /></td>
            <td><input type="number" placeholder="Nhập dữ liệu" /></td>
          </tr>
        </table>
      </div>
      <br />
      <br />
      <div class="box2">
        <table class="table2" id="myTable">
          <tr>
            <th>STT</th>
            <th>Nguyên Vật Liệu</th>
            <th>Số lượng</th>
            <th>Giá cả (VND)</th>
          </tr>
          <tr v-for="(row, index) in rows" :key="index" :class="`row-${index}`">
            <td>{{ index + 1 }}</td>
            <td><input type="text" placeholder="Nhập dữ liệu" /></td>
            <td><input type="number" placeholder="Nhập dữ liệu" /></td>
            <td><input type="number" placeholder="Nhập dữ liệu" /></td>
          </tr>
        </table>
      </div>
    </div>
    <button class="button1" @click="themHang()">Thêm Hàng</button>
    <button class="button2">Nộp Báo Cáo</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      rows: []
    }
  },
  methods: {
    themHang() {
      this.rows.push({})
    }
  }
}
</script>

<style scoped>
body {
  width: 100%;
  height: 100vh;
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}
.box1 {
  padding-top: 80px;
  display: flex;
  margin: 0;
  left: 0;
  align-items: center;
  justify-content: center;
  gap: 100px;
}

.box2 {
  display: flex;
  margin: 0;
  left: 0;
  align-items: center;
  justify-content: center;
}

table,
th,
td {
  border: 1px solid #333;
  border-collapse: collapse;
  text-align: center;
}
input {
  border: rgb(236, 244, 175);
  box-sizing: border-box;
  width: 100%;
  text-align: center;
  background-color: rgb(236, 244, 175);
}
.button1 {
  height: 30px;
  width: 100px;
  background-color: bisque;
  border-radius: 20px;
  justify-content: center;
  margin-left: 46%;
  margin-top: 20px;
}
.button1:hover {
  background-color: antiquewhite;
  transition: background-color 0.2s ease;
}
.button1:active {
  background-color: gray;
  transition: background-color 0.2s ease;
}
.button2 {
  height: 30px;
  width: 100px;
  background-color: bisque;
  justify-content: center
  border-radius: 20px;
  margin-left: 46%;
  margin-top: 10px;
}
.button2:hover {
  background-color: antiquewhite;
  transition: background-color 0.2s ease;
}
.button2:active {
  background-color: gray;
  transition: background-color 0.2s ease;
}
.table1 th {
  background-color: aquamarine;
}
.table1 td {
  background-color: rgb(236, 244, 175);
}
.table2 th {
  background-color: aquamarine;
}
.table2 td {
  background-color: rgb(236, 244, 175);
}
/* Add new row styles */
.table2 .row-0 td {
  background-color: rgb(236, 244, 175);
}
.table2 .row-1 td {
  background-color: rgb(236, 244, 175);
}
.table2 .row-2 td {
  background-color: rgb(236, 244, 175);
}
.table2 .row-3 td {
  background-color: rgb(236, 244, 175);
}
</style>
