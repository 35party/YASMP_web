<template>
  <v-row justify="center" align="center" class="pt-1">
    <v-col cols="12" sm="12" md="12">
      <v-card class="pb-4">
        <v-card-title class="headline">
          欢迎使用 YASMP&nbsp;
          <em class="text-subtitle-2 pt-1">Yet Another Simple Mod Pack</em>
        </v-card-title>
        <v-card-text>
          <p>本项目的主旨就是：做一个整合包，只要能用就行。</p>
          <div class="text-xs-right">
            所以这就是瞎糊出来的能用就行了要啥棒棒糖？<br />
            <em><small>&mdash; 一位不愿透露姓名的神秘人物</small></em>
          </div>
        </v-card-text>
        <v-card-actions class="px-4 pb-4">
          <v-btn color="primary" nuxt to="/modpack"> 下载最新版本整合包 </v-btn>
        </v-card-actions>
        <a href="https://vercel.com/?utm_source=35party&utm_campaign=oss" target="_blank" title="Sponsored by Vercel"><v-img src="vercel.svg" width="160" class="mx-4"></v-img></a>
      </v-card>
      
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'IndexPage',
  head() {
    return {
      title: '欢迎使用',
    }
  },
}
</script>
