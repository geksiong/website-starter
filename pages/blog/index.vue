<template>
  <div>
    <div v-for="doc in docs" :key="doc.slug">
      <span>( {{ doc.date }} )</span>
      <nuxt-link :to="doc.path">
        <strong>{{ doc.title }}</strong>
      </nuxt-link>
      <p>
        <em>{{ doc.excerpt }}</em>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const docs = await $content('blog')
      .sortBy('date', 'desc')
      .sortBy('title', 'desc')
      .fetch()
    // console.log('docs: ', docs)
    return { docs }
  },
}
</script>

<style></style>
