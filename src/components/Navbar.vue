<template>
  <div>
    <el-menu default-active="1" class="el-menu-demo" mode="horizontal" @select="handleSelect">
      <div class="navbar-brand" id="lt-navbar-logo">
        <div class="row">
          <div class="col-md-4 col-md-offset-0">
            <img src="../../static/images/icons/tcat_icon2.png" id="lt-navbar-icon">
          </div>
        </div>
        <div class="row" id="sa-tcat-icon">BusApp</div>
      </div>
      <el-menu-item index="1"><i class="fa fa-home"></i><span class="sr-only">(current)</span></el-menu-item>
      <el-menu-item index="2"><i class="fa fa-history"></i></el-menu-item>
      <el-menu-item index="3">What is BusApp?</el-menu-item>
    </el-menu>

    <!-- content -->
    <router-view :curr-game-level="currGameLevel"></router-view>
  </div>
</template>

<script>
  export default {
    props: ['currGameLevel'],
    data() {
      return {
        keyRoute: {
          1: "/",
          2: "/history",
          3: "/about",
          4: "/game/" + this.currGameLevel
        }
      }
    },
    methods: {
      handleSelect(key, keyPath) {
        this.$router.push(this.keyRoute[key + ""]);
      }
    }
  }
</script>

<style>
  #lt-navbar-icon {
    width: 6rem;
  }

  #lt-navbar-logo {
    padding-top: 5px;
    padding-left: 20px;
  }

  #sa-tcat-icon {
    text-align: center;
  }
</style>