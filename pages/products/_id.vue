<template>
  <div id="product">
    <img :src="product.image" />
    {{ product }}
  </div>
</template>

<script>
export default {
  name: 'SingleProduct',
  async asyncData ({ $axios, params }) {
    const product = await $axios.$get(`https://fakestoreapi.com/products/${params.id}`)
    return { product }
  }
}
</script>

<style scoped>
#product {
  @apply flex flex-wrap items-center
}
#product > div {
  @apply w-full lg:w-1/2
}
h1 {
  @apply text-5xl
}
img {

}
p {
  @apply max-w-xl
}
#price {

}
</style>
