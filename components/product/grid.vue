<template>
  <ul>
    <li v-for="product in products" :key="product.title">
      <nuxt-link :to="`/products/${product.id}`">
        <img :src="product.image" :alt="product.title">
        <h2>{{ product.title }}</h2>
        <p>{{ product.price }} €</p>
      </nuxt-link>
    </li>
  </ul>
</template>

<script>

export default {
  name: 'ProductsGrid',
  props: {
    products: {
      type: Array,
      default: () => []
    }
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
