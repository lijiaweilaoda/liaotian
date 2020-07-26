<template>
    <div class="chats">
        <h3>用户：{{nowUser.username}}</h3>
        <chatItem v-for="(item,index) in chatlist" :key="index" :chatitem='item'>
            {{item.chatcontent}}
        </chatItem>
        <chatinput :sentEvent='sentEvent'></chatinput>
    </div>
  
</template>
<script>
import chatinput from './chatinput'
import chatItem from './chatItem'
export default {
    props:['nowUser'],
    components:{
        chatinput,chatItem
    },
    data(){
        return{
            chatlist:[
                {
                   user:{
                        username:'小明',
                        headImg:require('../assets/img/1.jpg')
                   },
                   chatcontent:'吃了吗'
                }
            ]
        }
    },
    methods:{
       sentEvent:function(value){
           console.log(value)
           this.chatlist.push( {
                   user:{
                        username:'小明',
                        headImg:require('../assets/img/1.jpg')
                   },
                   chatcontent:value,
                //    user:this.$root.$children[0].nowUser,
                //    chatcontent:new Date()
                })
                this.chatlist.push( {
              
                  user:this.$root.$children[0].nowUser,
                    chatcontent:'好吃的很'
                })
       }
    }
  
}
</script>
<style scoped>
.chats{width: 500px;height: 600px;border: 2px solid palegreen;display: flex;position: relative;flex-direction:column}

</style>