<template>
  <v-app dark>
    <h1 v-if="error.statusCode === 404" class="text-h4 text-center pb-3">
      {{ pageNotFound }}
    </h1>
    <h1 v-else class="text-h4 text-center pb-3">
      {{ otherError }}
    </h1>
    <v-btn color="primary" nuxt to="/">返回首页</v-btn>
  </v-app>
</template>

<script>
export default {
  name: 'EmptyLayout',
  layout: 'empty',
  props: {
    error: {
      type: Object,
      default: null,
    },
  },
  data() {
    return {
      pageNotFound: '啊哦，你访问的页面找不到了',
      otherError: '发生了一个错误',
    }
  },
  head() {
    const title = this.error.statusCode === 404 ? '404 Not Found' : 'Error'
    return {
      title,
    }
  },
}
</script>
