<template>
<div class="page-header">
  <div class="page-header_bg" style="background-image: url('https://i1.wp.com/www.restaurant-alliance.fr/wp-content/uploads/2015/02/header.jpg?fit=1798%2C827&amp;ssl=1');"></div>
  <div class="page-header_in">
    <div class="page-header_item">
	  <div class="pheader_item_in">

	  </div>
    </div>
  </div>
</div>
</template>

<script>
  export default {
    data () {
      return {
	    
      }
    }
  }
</script>

<style>
.page-header {
  height: 35%;
  position: relative;
  width: 100%;
}

.page-header_bg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
}

.page-header_in {
    display: table;
    width: 100%;
    height: 100%;
    z-index: 2;
    position: relative;
}

.page-header_item {
  display: table-cell;
  text-align: center;
  vertical-align: middle;
  padding: 100px 0 20px 0;
}

.pheader_item_in {
    display: inline-block;
    padding: 0 15px;
}

</style>