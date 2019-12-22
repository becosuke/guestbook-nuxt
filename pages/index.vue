<template>
  <section>
    <div>
      <ul>
        <li v-for="item in items" :key="item.score">
          <dl>
            <dt>{{ item.name }}</dt>
            <dd>{{ item.body }}</dd>
          </dl>
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
export default {
  async asyncData({ app }) {
    const response = await app.$axios.$get('http://guestbook-nginx:8000/range')
    return { items: response }
  }
}
</script>

<style></style>
