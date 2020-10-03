<template>
  <div class="container">
    <article class="prose">
      <h1>{{ doc.title }}</h1>
      <p>
        <i>{{ doc.date }}</i>
      </p>
      <nuxt-content :document="doc" />
    </article>
    <div class="container flex justify-between">
      <span v-if="prev" class="text-teal-500 hover:underline">
        &lt; <nuxt-link :to="prev.slug">{{ prev.title }}</nuxt-link>
      </span>
      <span v-else></span>

      <span v-if="next" class="text-teal-500 hover:underline">
        <nuxt-link :to="next.slug">{{ next.title }}</nuxt-link> &gt;
      </span>
      <span v-else></span>
    </div>
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
