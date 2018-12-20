<template>
  <div id="app">
    <div class="navbar-001">
	  <div class="container">
	    <div class="row">
		  <div class="top-cover" v-if="visibleButton">
		    <button type="button" class="btn btn-dark" v-on:click="activate()">Показать</button>
		  </div>
		  
		  <div class="top-cover" v-if="!visible && !visibleButton">
			  <div class="content-bar">
				<div id="block_1" class="barlittle"></div>
				<div id="block_2" class="barlittle"></div>
				<div id="block_3" class="barlittle"></div>
				<div id="block_4" class="barlittle"></div>
				<div id="block_5" class="barlittle"></div>
			  </div>
		  </div>
		  
		      <div class=" col-xs-4 col-sm-4 col-md-12 center-block">
			    <div class="nekoAnim-animated nekoAnim-bounceIn fixed-top" data-nekodelay="100" v-if="visible">
				  <ul class="navbar menu navbar-inverse">
				    <li class="navbar-brand"><a href="#"  class="navbar-toggle">ГЛАВНАЯ</a></li>
				    <li><a href="#">О РЕСТОРАНЕ</a></li>
				    <li><a href="#">АНОНСЫ/НОВОСТИ</a></li>
				    <li><a href="#">СОБЫТИЯ</a></li>
			        <li><a href="#">ФОТООТЧЕТЫ</a></li>
				    <li><a href="#">КОНТАКТЫ</a></li>
				    <li class="lang form-inline"><a href="#">РУ / EN</a></li>			
				    <li class="search">
				      <form class="form-inline">
				        <input class="form-control mr-sm-2" type="search" placeholder="Поиск" aria-label="Search" v-if="visibleInput">
				        <button class="btn btn-link my-2 my-sm-0" type="submit"><img src="./assets/search.jpg" alt="Поиск" v-on:click="visibleInput=!visibleInput"/></a></button>
				      </form>
				    </li>
				  </ul>
			    </div>
		      </div>
              <div class="col-md-12 center-block" v-if="visible">
			    <b-carousel id="carousel1"
                style="text-shadow: 1px 1px 2px #333;"
                controls
                indicators
                background="#ababab"
                :interval="4000"
                v-model="slide"
                @sliding-start="onSlideStart"
                @sliding-end="onSlideEnd"  class="nekoAnim-animated nekoAnim-fadeInUp" data-nekodelay="100">
				  <b-carousel-slide caption='Добро пожаловать в "Монополь"'
                        text='Демократичное кафе с европейским и паназиатским меню'
                        img-src="https://i.ibb.co/VStJ05w/slider12.jpg">
				  </b-carousel-slide>
				  <b-carousel-slide img-src="https://picsum.photos/1024/480/?image=58">
				  </b-carousel-slide>
				  <b-carousel-slide>
					<img slot="img" class="d-block img-fluid w-100" width="1024px" height="480"
					src="https://picsum.photos/1024/480/?image=55" alt="image slot">
				  </b-carousel-slide>
			    </b-carousel>
			  </div>

		    </div>
	      </div>
	    </div>
      </div>
</template>


<script>
export default {
  data () {
    return {
      slide: 0,
      sliding: null
    }
  },
  methods: {
    onSlideStart (slide) {
      this.sliding = true
    },
    onSlideEnd (slide) {
      this.sliding = false
    }
  }
}
</script>

<script>
export default {
  name: 'app',
  data () {
    return {
	  visible: false,
	  visibleButton: true,
	  visibleInput: false
    }
  },
  methods: {
	  showAll: function () {
	    this.visible = true;
	  },
	  activate: function () {
		this.visibleButton = false;
		
		setTimeout(this.showAll, 5000);
	  }
	}
  }
</script>





<style>
.navbar-001 .container {
  padding-left: 0;
  padding-right: 0;
  margin-left: 0;
  margin-right: 0;
  max-width: 100%;
}

.navbar-001 .col-md-12 {
  padding-left: 0;
  padding-right: 0;
}

li a {
  color: #fff;
  font-size: 12px;
  text-decoration: none;
}

li a:hover,
li a:visited {
  text-decoration: none;
  color: #fff;
}

.navbar-001 {
  font-size: 16px;
  font-weight: 100;
  background-color: #8f3230;
}

.navbar-001 .menu {
  padding: 0;
}

.navbar-001 .navbar-inverse {
  background-color: #8f3230;
  color: #b1706f;
  border: none;
}

.navbar-001 .navbar-brand {
  padding: 5px 20px;
}

.b-carousel {
	width: 100%;
}

.navbar-001 .row {
  margin-left: 0;
  margin-right: 0;
}

.row .top-cover {
  width: 100px;
  display: flex;
  flex-direction: column;
  height: 100vh;
  margin-left: auto;
  margin-right: auto;
  position: relative;
}

.top-cover .btn {
	height: 50px;
    position: relative;
    top: 0;
    bottom: 0;
    margin: auto 0;
}

.lang, 
.search {
  list-style: none;
}

.carousel-item .carousel-caption {
	padding-bottom: 170px;
}

.navbar-001 .navbar {
  margin-bottom: 0;
}

.navbar-001 .content-bar {
	height: 50px;
	width: 200px;
    position: absolute;
    top: 0;
    bottom: 0;
    margin: auto 0;
	display: inline-block;
}

.navbar-001 .barlittle {
 background-color:#2187e7;  
 background-image: -moz-linear-gradient(45deg, #2187e7 25%, #a0eaff); 
 background-image: -webkit-linear-gradient(45deg, #2187e7 25%, #a0eaff);
 border-left:1px solid #111; border-top:1px solid #111; border-right:1px solid #333; border-bottom:1px solid #333; 
 width:20px;
 height:20px;
 float:left;
 margin-left:10px;
 opacity:0.1;
 -moz-transform:scale(0.7);
 -webkit-transform:scale(0.7);
 -moz-animation:move 1s infinite linear;
 -webkit-animation:move 1s infinite linear;
}

.navbar-001 #block_1 {
 -moz-animation-delay: .4s;
 -webkit-animation-delay: .4s;
 }
 
.navbar-001 #block_2 {
 -moz-animation-delay: .3s;
 -webkit-animation-delay: .3s;
}

.navbar-001 #block_3 {
 -moz-animation-delay: .2s;
 -webkit-animation-delay: .2s;
}

.navbar-001 #block_4 {
 -moz-animation-delay: .3s;
 -webkit-animation-delay: .3s;
}

.navbar-001 #block_5 {
 -moz-animation-delay: .4s;
 -webkit-animation-delay: .4s;
}

@-moz-keyframes move {
 0%{-moz-transform: scale(1.2);opacity:1;}
 100%{-moz-transform: scale(0.7);opacity:0.1;}
}

@-webkit-keyframes move {
 0%{-webkit-transform: scale(1.2);opacity:1;}
 100%{-webkit-transform: scale(0.7);opacity:0.1;}
}
</style>
