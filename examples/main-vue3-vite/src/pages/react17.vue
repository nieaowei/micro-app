<template>
<div class="react17">
  <micro-app
    name='react17'
    url='http://localhost:3002/'
    :data='data'
  >
    <!-- destory inline -->
  </micro-app>
</div>
</template>

<script lang="ts" setup>
import {ref} from "vue";

const data = ref({from: '来自基座的初始化数据'})
</script>

<style>

</style>
