<template>
  <div>
    <h1>Selamat datang di Toko Online Kami!</h1>
    <p>Temukan berbagai produk menarik kami di sini.</p>
    <button class="w-5 h-6" @click="goToProducts">Lihat Produk</button>
  </div>
</template>

<script>
export default {
  methods: {
    goToProducts() {
      this.$router.push('/products')
    },
  },
}
</script>
// export default { // name: 'IndexPage', // }
