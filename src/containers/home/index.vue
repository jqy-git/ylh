<template>
  <div>
    <div id="center">
      <el-button type="text" @click="open">点击打开 Message Box</el-button>
      <a href="">登录</a>
    </div>
    <div id="bottom">
      <span class="mane">宁波优城悦邻商业运营管理有限责任公司</span>
      <span class="bah">浙ICP备20010478号</span><br />
      <span class="address"
        >地址浙江省宁波市鄞州区中山东路2622号甬江人才创新中心1号楼19层</span
      >
    </div>
  </div>
</template>

<script>
export default {
  name: "test",
  components: {},
  data() {
    return {};
  },
  methods: {
    open() {
      const h = this.$createElement;
      this.$msgbox({
        title: "消息",
        message: h("p", null, [
          h("span", null, "内容可以是 "),
          h("i", { style: "color: teal" }, "VNode"),
        ]),
        showCancelButton: true,
        confirmButtonText: "确定",
        cancelButtonText: "取消",
        beforeClose: (action, instance, done) => {
          if (action === "confirm") {
            instance.confirmButtonLoading = true;
            instance.confirmButtonText = "执行中...";
            setTimeout(() => {
              done();
              setTimeout(() => {
                instance.confirmButtonLoading = false;
              }, 300);
            }, 3000);
          } else {
            done();
          }
        },
      }).then((action) => {
        this.$message({
          type: "info",
          message: "action: " + action,
        });
      });
    },
  },
};
</script>

<style lang="less">
#bottom {
  font-size: 10px;
  width: 100%;
  height: 50px;
  // background-color: #666666;
  text-align: center;
  line-height: 25px;
}
</style>