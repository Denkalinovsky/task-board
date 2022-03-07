<template>
  <div>
    <el-button @click="drawer = true" type="primary" style="margin-left: 16px">
      Open
    </el-button>
    <el-drawer
      title="I am the title"
      :visible.sync="drawer"
      :with-header="false"
    >
      <span>Тест</span>
    </el-drawer>
  </div>
</template>

<script>
export default {
  name: "RightMenu",
  data() {
    return {
      drawer: false,
    };
  },
};
</script>
