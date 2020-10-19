<template>
    <div id="login">
        <div class="login-wrap">
            <ul class="menu-tab">
                <li v-for="item in menuTab" :class="{'current': item.current}" :key='item.id' @click="toggleMenu(item)">
                    {{item.txt}}
                </li>
            </ul>
        </div>
    </div>
</template>
<script >
export default {
  name: "login",
  data(){
      return{
          menuTab:[
              {txt: '登录', current: true},
              {txt: '注册', current: false}
          ]
      }
  },
  methods:{
      toggleMenu(data){
          this.menuTab.forEach(element => {
              element.current = false;
          });
          data.current = true;
      }
  }
};
</script>
<style scoped lang='scss'>
#login{
    height: 100vh;
    background-color: #344a5f;
    }
.login-wrap{
    width: 330px;
    border-color: black;
    border-style: solid;
    margin: auto;
    list-style: none;
    }
.menu-tab{
    text-align: center;
    li{
        display: inline-block;
        width: 88px;
        line-height: 36px;
        color: #ffffff;
        border-radius: 2px;
        font-size: 14px;
    }
    .current{
        background-color: rgba(0,0,0,.1);
    }
}
</style>