<template>
    <div class="col-3 item-card">
        <img class="item-img" @click="toItemDetailsPage()" src="https://thiscatdoesnotexist.com/"/>
        <div class="row">
            <p class="name col-9">Cat T-shirt</p>
            <i class="heart mdi mdi-cards-heart-outline col-3" v-if="!outlined" @click=toggleHeart() ></i>
            <i class="heart mdi mdi-cards-heart" v-if="outlined" @click=toggleHeart()></i>
        </div>
        <p class="price">$150</p>
    </div>


</template>
 
<script>
import { router } from '../router'
import { logger } from '../utils/Logger'
import Pop from '../utils/Pop'

export default {
   setup(){
      return {
        toItemDetailsPage(){
            try {
                        // params: { id: AppState.user.id }
               router.push({name: 'ItemDetails', params: {id: '1'}})
            }
            catch (error) {
               logger.error(error)
               Pop.toast(error.message, 'error')
            }
        },
        toggleHeart(){
            try {
                this.outlined = !this.outlined;
            }
            catch (error) {
               logger.error(error)
               Pop.toast(error.message, 'error')
            }
        }
      }
   }
}
</script>
 
<style> 
.item-img{
    width: -webkit-fill-available;
    cursor: pointer;
}
.item-card{
    position: relative;
    margin-bottom: 5vh;
    /* background-color: rgb(205, 205, 205); */
    /* border-style:  solid; */
    /* border-color: red; */   
    transition: transform 250ms;
}
.item-card:hover{
    transform: translateY(-3px);
}
.name{
    /* position: absolute; */
    font-size: large;
    font-weight: 400;
    margin: 0;
}
.heart{
    font-size: 25px;
    transition: transform 250ms;
}
.heart:hover{
    transform: translateY(-3px);
    cursor: pointer;
}
.price{
    /* position: absolute; */
    font-size: 21px;
    font-weight: 500;
    /* bottom: -12vh; */
}
</style>