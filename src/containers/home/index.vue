<template>
  <div>
    <span @click="sign">注册</span>
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
      sign(){
          this.$router.push({
              path:"/register"
          })
      }
  }
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