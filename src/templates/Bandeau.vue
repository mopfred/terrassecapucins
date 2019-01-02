<template>
<div class="page-header">
  <div class="page-header_bg" style="background-image: url('https://i1.wp.com/www.restaurant-alliance.fr/wp-content/uploads/2015/02/header.jpg?fit=1798%2C827&amp;ssl=1');"></div>
  <div class="page-header_in">
    <div class="page-header_item">
	  <div class="pheader_item_in">
        <transition name="slide-fade" mode="out-in">
		  <div class="font" v-if="tab === 'home'">
	        {{ titleUp }}
	      </div>
		</transition>
		<transition name="slide-fade" mode="out-in">
		  <div class="font" v-if="tab === 'menu'">
	        {{ titleUp }}
	      </div>
		</transition>
		<transition name="slide-fade" mode="out-in">
		  <div class="font" v-if="tab === 'portfolio'">
	        {{ titleUp }}
	      </div>
	    </transition>
		<transition name="slide-fade" mode="out-in">
		  <div class="font" v-if="tab === 'admin'">
	        {{ titleUp }}
	      </div>
	    </transition>
		<div class="page-title_separator">
		  <div class="ptitle-separator_container">
			<div class="ptitle-separator_in">
			  <div class="ptitle-separator_item">
				<div class="ptitle-separator_line"/>
			  </div>
			  <span class="ptitle-separator_icon"/>
			  <div class="ptitle-separator_item">
				<div class="ptitle-separator_line"/>
			  </div>
			</div>
		  </div>
		</div>
		<transition name="slide-fade" mode="out-in">
	      <div class="font" v-if="tab === 'home'">
	        {{ titleDown }}
	      </div>
		</transition>
		<transition name="slide-fade" mode="out-in">
		  <div class="font" v-if="tab === 'menu'">
	        {{ titleDown }}
	      </div>
		</transition>
		<transition name="slide-fade" mode="out-in">
		  <div class="font" v-if="tab === 'portfolio'">
	        {{ titleDown }}
	      </div>
	    </transition>
		<transition name="slide-fade" mode="out-in">
		  <div class="font" v-if="tab === 'admin'">
	        {{ titleDown }}
	      </div>
	    </transition>
	  </div>
    </div>
  </div>
</div>
</template>

<script>
  export default {
    props: {
      tab: String,
      titleUp: String,
      titleDown: String
    },
    data () {
      return {
      }
    }
  }
</script>

<style>
.font{
  font-family: "Cookie";
  font-weight: 400;
  font-size: 72px;
  line-height: 55px;
  color: #ffffff;
  margin-bottom: 34px;
}

.slide-fade-enter-active {
  transition: all 3s ease;
}

.slide-fade-leave-active {
  transition: all 0s cubic-bezier(0, 0, 0, 0);
}

.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateX(-50px);
  opacity: 0;
}

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

.page-title_separator {
    min-height: 10px;
    position: relative;
}

.ptitle-separator_container {
    position: absolute;
    left: 0;
    width: 100%;
}

.ptitle-separator_in {
    display: table;
    width: 100%;
}

.ptitle-separator_item {
    display: table-cell;
    width: 50%;
    vertical-align: middle;
}

.ptitle-separator_line {
    background: #ffffff;
    width: 100%;
    height: 1px;
}

.ptitle-separator_icon {
    display: table-cell;
    padding: 0 7px;
}

</style>
