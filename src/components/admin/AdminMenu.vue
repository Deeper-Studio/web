<template>
<!--  <el-menu-->
<!--    :default-active="currentPath"-->
<!--    class="el-menu-admin"-->
<!--    router-->
<!--    mode="vertical"-->
<!--    background-color="#545c64"-->
<!--    text-color="#fff"-->
<!--    active-text-color="#ffd04b"-->
<!--    :collapse="isCollapse">-->
<!--    <div style="height: 80px;"></div>-->
<!--      &lt;!&ndash;index 没有用但是必需字段&ndash;&gt;-->
<!--&lt;!&ndash;    <el-submenu  v-for="(item,i) in adminMenus" :key="i" :index="(i).toString()" style="text-align: left">&ndash;&gt;-->
<!--      <el-submenu  v-for="(item,i) in adminMenus" :key="i" :index="(i).toString()" style="text-align: left">-->
<!--        <span slot="title" style="font-size: 17px;">-->
<!--          <i :class="item.iconCls"></i>-->
<!--          {{item.nameZh}}-->
<!--        </span>-->
<!--        <el-menu-item v-for="child in item.children" :key="child.path" :index="child.path">-->
<!--          <i :class="child.icon"></i>-->
<!--          {{ child.nameZh }}-->
<!--        </el-menu-item>-->
<!--      </el-submenu>-->
<!--  </el-menu>-->
  <el-menu
    default-active="2"
    class="el-menu-vertical-demo"
    @open="handleOpen"
    @close="handleClose"
    background-color="#545c64"
    text-color="#fff"
    active-text-color="#ffd04b">
    <el-submenu index="1" style="margin-top: 80px">
      <template slot="title">
        <i class="el-icon-location"></i>
        <span>Paper Management</span>
      </template>
      <el-menu-item-group>
        <router-link to="/admin/review">
          <el-menu-item >Review</el-menu-item>
        </router-link>
      </el-menu-item-group>
    </el-submenu>
  </el-menu>
</template>

<script>
    export default {
      name: 'AdminMenu',
      data () {
        return {
          isCollapse: false,
          adminMenus: {}
        }
      },
      methods: {
        handleOpen (key, keyPath) {
          console.log(key, keyPath)
        },
        handleClose (key, keyPath) {
          console.log(key, keyPath)
        }
      }
      // computed: {
      //   adminMenus () {
      //     return this.$store.state.adminMenus
      //   },
      //   currentPath () {
      //     return this.$route.path
      //   }
      // }
    }
</script>

<style scoped>
  .el-menu {
    border-radius: 5px;
    height: 100%;
  }
</style>
