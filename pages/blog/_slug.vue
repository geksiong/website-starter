<template>
  <div class="container">
    <nuxt-content :document="doc" />
    <hr />
    <h5 v-if="prev">
      &lt; <nuxt-link :to="prev.slug">{{ prev.title }}</nuxt-link>
    </h5>
    <h5 v-if="next">
      <nuxt-link :to="next.slug">{{ next.title }}</nuxt-link> &gt;
    </h5>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    // console.log(params.slug)
    const doc = await $content(`blog/${params.slug}` || 'index').fetch()
    const [prev, next] = await $content('blog')
      .only(['title', 'slug'])
      .sortBy('date', 'asc')
      .sortBy('title', 'asc')
      .surround(params.slug, { before: 1, after: 1 })
      .fetch()
    return { doc, prev, next }
  },
}
</script>

<style></style>
