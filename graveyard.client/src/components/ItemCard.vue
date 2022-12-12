<template>
    <div class="col-3 item-card">
        <img src="https://thiscatdoesnotexist.com/"/>
        <p class="name">Cat</p>
        <p class="price">$150</p>
    </div>


</template>
 
<script>

export default {
   setup(){
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
    background-color: rgb(205, 205, 205);
    
}
.name{
    font-size: large;
    font-weight: 400;
}
.price{
    font-size: medium;
    font-weight: 500;
}
</style>