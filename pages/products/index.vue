<template>
  <div>
    <product-grid :products="products" />
  </div>
</template>

<script>
export default {
  name: 'ProductsGrid',
  async asyncData ({ $axios }) {
    const products = await $axios.$get('https://fakestoreapi.com/products')
    return { products }
  }
}
</script>

<style scoped>
ul{
  @apply grid grid-cols-1 lg:grid-cols-3 xl:grid-cols-4 gap-4
}

li {
  @apply text-center
}

img {
  @apply m-auto
}
</style>

