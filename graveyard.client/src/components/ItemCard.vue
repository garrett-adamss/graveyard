<template>
    <div class="col-3 item-card">
        <img class="item-img" src="https://thiscatdoesnotexist.com/"/>
        <p class="name">Cat T-shirt</p>
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
.item-img{
    width: -webkit-fill-available;
}
.item-card{
    position: relative;
    margin-bottom: 10vh;
    /* background-color: rgb(205, 205, 205); */
    /* border-style:  solid; */
    /* border-color: red; */   
    transition: transform 250ms;
}
.item-card:hover{
    transform: translateY(-4px);
    cursor: pointer;
}
.name{
    position: absolute;
    font-size: large;
    font-weight: 400;
}
.price{
    position: absolute;
    font-size: 21px;
    font-weight: 500;
    bottom: -12vh;
}
</style>