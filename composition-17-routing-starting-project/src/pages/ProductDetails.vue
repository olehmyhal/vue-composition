<template>
  <section>
    <h2>{{ title }}</h2>
    <h3>${{ price}}</h3>
    <p>{{ description}}</p>
  </section>
</template>

<script>
import { inject } from 'vue';
import { useRoute } from 'vue-router'

export default {
  props: ['pid'],
  setup(props) {
    const products = inject('products')

    const route = useRoute()
    console.log(route)

    const selectedProduct = products.value.find(product => product.id === props.pid)
    const { title, price, description } = selectedProduct

    return { title, price, description };
  },
};
</script>


<style scoped>
section {
  margin: 3rem auto;
  max-width: 40rem;
  padding: 1rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
}
</style>