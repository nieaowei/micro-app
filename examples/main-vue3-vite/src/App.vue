<template>
<div class="menu-con">
  <el-menu
    class="el-menu-vertical-demo"
    :router='true'
    :default-active='activeIndex'
  >
    <el-menu-item index="/react16/">
      <i class="el-icon-present"></i>
      <span slot="title">react16</span>
    </el-menu-item>
    <el-menu-item index="/react17/">
      <i class="el-icon-menu"></i>
      <span slot="title">react17</span>
    </el-menu-item>
    <el-menu-item index="/vue2/">
      <i class="el-icon-document"></i>
      <span slot="title">vue2</span>
    </el-menu-item>
    <el-menu-item index="/vue3/">
      <i class="el-icon-setting"></i>
      <span slot="title">vue3</span>
    </el-menu-item>
    <el-menu-item index="/vite/">
      <i class="el-icon-setting"></i>
      <span slot="title">vite</span>
    </el-menu-item>
    <el-menu-item index="/angular11/">
      <i class="el-icon-picture-outline"></i>
      <span slot="title">angular11</span>
    </el-menu-item>
    <el-menu-item index="/multiple/">
      <i class="el-icon-s-cooperation"></i>
      <span slot="title">multiple</span>
    </el-menu-item>
    <el-menu-item index="/self/">
      <i class="el-icon-s-platform"></i>
      <span slot="title">self</span>
    </el-menu-item>
  </el-menu>
</div>
<div class="router-con">
  <router-view/>
</div>
</template>

<script lang="ts" setup>
import {onMounted, onUpdated, ref, watch} from "vue";
import {useRouter} from 'vue-router'

const activeIndex = ref('/react16/')
const {currentRoute} = useRouter()
watch(currentRoute, (newVal, oldVal) => {
  activeIndex.value = currentRoute.value.fullPath
})

onUpdated(() => {
  const es = document.getElementsByTagName("micro-app")
  for (let i = 0; i < es.length; i++) {
    es[i].setAttribute("name", es[i].getAttribute("name"))
    es[i].setAttribute("url", es[i].getAttribute("url"))
  }
})

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  background: #fff;
  width: 100%;
  /* padding: 10px; */
  box-sizing: border-box;
  display: flex;
}

.menu-con {
  width: 200px;
}

.router-con {
  flex: 1;
}

body {
  margin: 0;
}
</style>
