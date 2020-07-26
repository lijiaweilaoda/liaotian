<template>
    <div class="chatitemo">
        <img :src="chatitem.user.headImg">
        <div>
            <slot></slot>
        </div>
    </div>
</template>
<style  scoped>
.chatitemo{
  height: 50px;background-color:palevioletred;width: 100%;border: 1px solid black;
}
.chatitemo img{width:40px;height: 40px;}
.chatitemo{display: flex;}
</style>
<script>
export default {
    props:['chatitem']
}
</script>