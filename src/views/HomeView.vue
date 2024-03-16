<template>
  <div>
    <h1>Welcome to Chicken's Company</h1>
    <div class="wrapper"></div>
    <form>
      <br />
      <br />
      <h2>
        <div class="form-field">
          <input
            type="text"
            class="form-input"
            name="user"
            id="user"
            size="29"
            placeholder=" "
            required
          />
          <label for="name" class="form-label">Tài Khoản đăng nhập</label>
        </div>
      </h2>
      <br />
      <br />
      <div class="form-field">
        <input
          type="password"
          class="form-input"
          name="password"
          id="password"
          size="29"
          placeholder=" "
          required
        />
        <label for="name" class="form-label">Mật khẩu đăng nhập</label>
        <br />
      </div>
      <br />
      <div>
        <button class="button" type="button" @click="accountpassword()">Đăng nhập</button>
        <p class="textwarning" id="Result"></p>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  methods: {
    accountpassword() {
      const list = [
        { user: 'morriskayer', password: '210505' },
        { user: 'chococomilk', password: '140305' },
        { user: 'thienphu', password: '210505210505' }
      ]
      var user = document.getElementById('user').value
      var password = document.getElementById('password').value
      if (list.some((item) => item.user === user && item.password === password)) {
        window.location.href = 'about'
        window.close()
      } else if (user === '' && password === '') {
        document.getElementById('Result').innerHTML = 'Vui lòng nhập Tài khoản và Mật Khẩu!'
      } else {
        document.getElementById('Result').innerHTML =
          'Thông tin đăng nhập không đúng. Vui lòng kiểm tra lại'
      }
    }
  }
}
</script>
