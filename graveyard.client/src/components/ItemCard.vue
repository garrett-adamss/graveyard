<template>
    <div class="col-md-3 item-card" @click="toItemsDetailPage()">
        <img src="https://thiscatdoesnotexist.com/"/>
        <div class="text-box">
            <p class="name">Cat</p>
            <p class="price">$150</p>
        </div>
    </div>


</template>
 
<script>

export default {
   setup(){
    // toItemsDetailPage(){
    //     try {
           
    //     }
    //     catch (error) {
    //        logger.error(error)
    //        Pop.toast(error.message, 'error')
    //     }
    // }
      return {
        
      }
   }
}
</script>
 
<style> 
img{
    width: -webkit-fill-available;
}
.item-card{
    position: relative;
    background-color: rgb(205, 205, 205);
    border-style: solid;
    border-color: red;
}
.text-box{
    position: absolute;
}
.name{
    position: absolute;
    bottom: 0;
    font-size: large;
    font-weight: 400;
}
.price{
    position: absolute;
    bottom: 0;
    font-size: medium;
    font-weight: 500;
}
</style>