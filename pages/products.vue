<template>
  <div>
    <h2>Daftar Produk</h2>
    <div class="dropdown dropdown-bottom">
      <label tabindex="0" class="btn m-1">Pilih Kategori</label>
      <ul
        tabindex="0"
        class="dropdown-content z-[1] menu p-2 shadow bg-base-100 rounded-box w-52"
      >
        <li><a @click="filterByCategory(null)">Semua</a></li>
        <li><a @click="filterByCategory('Makanan')">Minuman</a></li>
        <li><a @click="filterByCategory('Elektronik')">Elektronik</a></li>
        <li><a @click="filterByCategory('Minuman')">Minuman</a></li>
      </ul>
    </div>
    <ul>
      <li v-for="(product, index) in filteredProducts" :key="index">
        {{ product.name }} - Rp{{ product.price }} - Kategori:
        {{ product.category }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [
        { name: 'kopi', price: 100000, category: 'Makanan' },
        { name: 'Iphone X', price: 150000, category: 'Elektronik' },
        { name: 'Madu', price: 200000, category: 'Minuman' },
      ],
      selectedCategory: null,
    }
  },
  computed: {
    filteredProducts() {
      if (!this.selectedCategory) {
        return this.products
      }
      return this.products.filter(
        (product) => product.category === this.selectedCategory
      )
    },
  },
  methods: {
    filterByCategory(category) {
      this.selectedCategory = category
    },
  },
}
</script>
