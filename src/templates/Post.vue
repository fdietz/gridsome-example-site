<template>
  <Layout>
    <h1 v-html="$page.post.title"></h1>
    <h3>{{$page.post.date}}</h3>
    <div v-html="$page.post.content" />
  </Layout>
</template>

<script>
export default {
  metaInfo() {
    return {
      title: this.$page.post.title
    }
  }
}
</script>

<page-query>
query Post($id: ID!) {
  post(id: $id) {
    title
    date
    content
  }
}
</page-query>