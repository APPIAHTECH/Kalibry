<template>
  <el-container>
    <Editor></Editor>

    <el-footer></el-footer>
  </el-container>
</template>

<style>
.el-footer{
  background-color: #545c64;
}
</style>

<script>
import Editor from '~/components/editor/Editor.vue'

export default {
  components: {
    Editor
  }
}
</script>