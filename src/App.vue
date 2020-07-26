<template>
  <div id="app">
    <div class="center">
        <chat-com :nowUser="nowUser"></chat-com>
        <user-list :ulist='list' @choseuser="toogeuser"></user-list> 
    </div>
        
    <router-view/>
  </div>
</template>

<script>
import chatCom from './components/chatcom'
import userList from './components/userlist'
export default {
  name: 'app',
  components:{
    chatCom,userList
  },
  data(){
    return {
      msg:'聊天',
      nowUser:{
          username:'小明',
          headImg:require('./assets/img/1.jpg')
      },
      list:[
        {
          username:'小明',
          headImg:require('./assets/img/1.jpg')
        },
        {
          username:'小红',
          headImg:require('./assets/img/2.jpg')
        },{
          username:'小绿',
          headImg:require('./assets/img/3.jpg')
        },{
          username:'小蓝',
          headImg:require('./assets/img/4.jpg')
        }
      ]
    }
  },
  methods:{
    toogeuser:function(index){
     console.log(index)
      this.nowUser=this.list[index]
    }
  }
}
</script>

<style scoped>
.center{width: 800px;height: 600px;display: flex;margin: 0 auto;}
</style>
