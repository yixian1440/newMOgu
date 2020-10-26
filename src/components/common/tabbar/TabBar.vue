<template>
 
  <div id="tab-bar">
  <slot></slot>
  </div>    
</template>

<script>
    export default{
    name:'TabBar'
}
</script>


<style scoped>

#tab-bar{
  display: flex;
  text-align: center;
  height: 49px;
  background-color: #f6f6f6;
  position: fixed;
  left: 0;
  bottom: 0;
  right: 0;
  box-shadow: 0px -2px 1px rgba(60,34,52, .1);
}

</style>

