<template>
  <div>
    <el-menu
      class="nav"
      mode="horizontal"
      background-color="#545c64"
      text-color="#fff"
      active-text-color="#fff"
      default-active="1"
    >
      <el-menu-item @click="to('/')" index="1">
        Home
      </el-menu-item>
      <el-menu-item @click="to('/porto')" index="2">
        Works
      </el-menu-item>
      <el-menu-item style="float:right">
        <a target="_blank" href="https://twitter.com/muh_muflih">Twitter</a>
      </el-menu-item>
      <el-menu-item style="float:right">
        <a target="_blank" href="https://www.linkedin.com/in/muhammad-muflih-574b2b71">Linkedin</a>
      </el-menu-item>
      <el-menu-item style="float:right">
        <a target="_blank" href="https://www.instagram.com/m_muflih5/">Instagram</a>
      </el-menu-item>
      <el-menu-item style="float:right">
        <a target="_blank" href="https://github.com/mmuflih55">Github</a>
      </el-menu-item>
    </el-menu>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeIndex: "1"
    };
  },
  methods: {
    to(path){
      this.$router.push(path)
    },
    handleSelect(key, keyPath) {
      console.log(key, keyPath);
    }
  }
};
</script>

<style scoped>
.nav a {
  text-decoration: none !important;
}
</style>
