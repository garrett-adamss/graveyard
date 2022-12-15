<template>
 <div class="offcanvas offcanvas-end" tabindex="-1" id="offcanvasRight" aria-labelledby="offcanvasRightLabel">
  <div class="offcanvas-header">
    <h5 class="offcanvas-title" id="offcanvasRightLabel">Shopping Cart</h5>
    <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>
  </div>
  <div class="offcanvas-body">
    <h1>shopping cart item go here</h1>
    <button class="checkout-button btn btn-outline-success" @click="toCheckoutPage()" data-bs-toggle="offcanvas">Checkout</button>
    <button class="clear-cart-button btn btn-outline-danger">Clear Cart</button>
  </div>
</div>
</template>
 
<script>
import { router } from '../router'
import { logger } from '../utils/Logger'
import Pop from '../utils/Pop'
export default {
   setup(){
      return {
        toCheckoutPage(){
            try {
               router.push({name: 'Checkout'})
               
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
.offcanvas-body{
    position: relative;
}
.checkout-button{
    position: absolute;
    bottom: 3vh;
}
.clear-cart-button{
    position: absolute;
    bottom: 3vh;
    right: 2vw;
}
</style>