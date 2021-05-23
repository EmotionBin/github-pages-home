<template>
  <div id="app">
    <div class="list-wrap">
      <div class="list-container">
        <template v-for="(item, index) in list">
          <div :key="index" class="list-item" @click="handleGo(item)">
            <div class="item-icon" :style="{'background-image':`url(${item.icon})`}"></div>
            <div class="item-title">{{ item.title }}</div>
          </div>
        </template>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      list: [
        {
          title: '我的博客',
          icon: '/icon/blog.svg',
          path: 'https://emotionbin.github.io/blog/'
        }
      ]
    }
  },
  components: {
  },
  methods: {
    // 跳转
    handleGo({path}){
      window.location.href = path
    }
  },
}
</script>

<style>
#app{
  display: flex;
  height: 100vh;
  background-color: #eee;
  padding: 10px;
}
.list-wrap{
  flex: 1;
}
.list-container{
  width: 25%;
}
.list-item{
      display: flex;
    flex-direction: column;
  width: 100%;
  height: 200px;
  cursor: pointer;
}
.item-icon{
      height: 150px;
  background-size: contain;
  background-position: center;
  background-repeat: no-repeat;
}
.item-title{
  font-size: 16px;
    color: #666;
      flex: 1;
    display: flex;
    align-items: center;
    justify-content: center;
}
</style>
