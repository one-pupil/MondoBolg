
<template>
  <el-dialog class="dialog" title="图片上传" :visible.sync="dialogVisible" :before-close="handleClose">
    <input class="hidden" type="file" id="file" @change="uploadMySelf($event)">
    <label for="file">
      <i class="el-icon-upload2"></i>
    </label>
  </el-dialog>
</template>
<style lang="less" rel="stylesheet/less" scope>
  .dialog {
    .el-dialog__body {
      text-align: center;
    }
    label {
      padding: 20px;
      border: 1px dashed #d9d9d9;
      border-radius: 3px;
      cursor: pointer;
      position: relative;
      overflow: hidden;
    }
  }
</style>
<script type='text/ecmascript-6'>
  export default {
    name: 'MoUploadDialog',
    props: ['dialogVisible'],
    methods: {
      handleClose() {
        this.$store.commit('SET_DIALOG', false);
      },
      uploadMySelf(e) {
        this.$emit('upload', e);
      }
    }
  };
</script>
