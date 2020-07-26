<template>
    <div class="userlist">
        <h1>用户列表</h1>
        <ul>
            <li v-for="(item,index) in ulist" :key="'userlist'+index" @click="choseUser(index)">
                <img :src="item.headImg" alt="">
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    data(){
     return{

     }
    },
    props:['ulist'],
    methods:{
        choseUser:function(index){
            console.log(index)
            this.$emit('choseuser',index)
        }
    }

}
</script scoped>
<style>
.userlist{width: 300px;height: 600px;background-color: aquamarine;border: 2px solid palegreen;}
.userlist ul li{display: flex;}
.userlist ul li img{width: 80px;height: 80px;}
</style>