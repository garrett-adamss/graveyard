<template>
  <h1>GraveYardBoise</h1>
  <div class="container-fluid">
    <div class="row">
      <div class="col-2">
        <div class="input-group rounded">
          <input type="search" class="form-control rounded" placeholder="Search" aria-label="Search" aria-describedby="search-addon" />
          <span class="input-group-text border-0" id="search-addon">
          <i class="mdi mdi-search"></i>
          </span>
        </div>
      </div>
      <div class="col-10">
        <div class="row">
          <ItemCard/>
          <ItemCard/>
          <ItemCard/>
           <ItemCard/>
          <ItemCard/>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
export default {

}
</script>

<style>

</style>