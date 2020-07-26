<template>
    <div class="chatlist">
        <input type="text" @keydown.enter="sent" v-model="inputConent">
        <button @click="sent">发送</button>
    </div>
</template>
<script>
export default {
    props:['sentEvent'],
    data(){
        return{
            inputConent:""
        }
    },
    methods:{
        sent:function(){
            this.sentEvent(this.inputConent)
            this.inputConent=""
        }
    }
}
</script>
<style scoped>
.chatlist{position: absolute;left: 0;top: 395px;}
.chatlist input{width: 488px;height: 200px;position: relative;}
.chatlist button{position: absolute;left: 400px;top: 180px;width: 80px;}
</style>