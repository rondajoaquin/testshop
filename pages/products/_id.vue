<template>
  <div id="product">
    <div>
      <img/>
    </div>
    <div>

    </div>
  </div>
</template>

<script>
export default {
  name: "SingleProduct",
  async asyncData ({ $axios, params }) {
    const product = await $axios.$get(`https://fakestoreapi.com/products/${params.id}`);
    return { product };
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
  @apply pr-15
}
p {
  @apply max-w-xl
}
#price {

}
</style>
