<template>
  <v-row justify="center" align="center" class="pt-1">
    <v-col cols="12" sm="12" md="12">
      <v-card class="text-center">
        <v-card-text>
          <h1 class="pa-4">整合包下载</h1>
          <div v-for="modPackList in lists" :key="modPackList.categoryName" class="py-4">
            <h2 class="text-center">{{ modPackList.categoryName }}</h2>
            <v-simple-table>
              <thead>
                <tr>
                  <th class="text-center">版本</th>
                  <th class="text-center">更新时间</th>
                  <th class="text-center">MultiMC</th>
                  <th class="text-center">通用整合包</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <td>{{ modPackList.version }}</td>
                  <td>{{ modPackList.lastUpdate }}</td>
                  <td><a :href="modPackList.downloadLink.multimc?modPackList.downloadLink.multimc:null">{{modPackList.downloadLink.multimc?'下载':'暂不可用'}}</a></td>
                  <td><a :href="modPackList.downloadLink.universal?modPackList.downloadLink.universal:null">{{modPackList.downloadLink.universal?'下载':'暂不可用'}}</a></td>
                </tr>
              </tbody>
            </v-simple-table>
          </div>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
import axios from 'axios'

export default {
  name: 'ModListPage',
  data() {
    return {
      lists: '',
    }
  },
  head() {
    return {
      title: 'Mod 整合下载',
    }
  },
  mounted() {
    axios.get('modpack.json').then((res) => {
      console.log(res.data)
      this.lists = res.data.modPackList
    })
  },
}
</script>
