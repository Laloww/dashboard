<template>
  <div>
    <div class="container left__nav" :class="[showNav == true ? 'show' : 'hide']">
      <div class="row ">
        <div class="col-12">
            <div class="button" style="margin-left:210px; cursor: pointer;" @click="showHide()"> 
                <div class="hamburger">
                <span class="hamburger__item" :class="[showNav == true ? 'hamburger__item_active' : '']"></span>
                <span class="hamburger__text" :class="[showNav == true ? 'hamburger__text_active' : '']"></span>
              </div> 
            </div>
            <ul class="nav flex-column">
                <li class="nav-item">
                    <a class="nav-link" href="#">Active <img src="http://ok-gid.ru/wp-content/uploads/2017/07/png-kartinka-odnoklassniki.png" width="28"></a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#">Link<img src="http://ok-gid.ru/wp-content/uploads/2017/07/png-kartinka-odnoklassniki.png" width="28"></a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#">Link<img src="http://ok-gid.ru/wp-content/uploads/2017/07/png-kartinka-odnoklassniki.png" width="28"></a>
                </li>
                <li class="nav-item">
                    <a class="nav-link disabled" href="#">Disabled<img src="http://ok-gid.ru/wp-content/uploads/2017/07/png-kartinka-odnoklassniki.png" width="28"></a>
                </li>
            </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
        showNav:true
    }
  },
  methods:{
      showHide: function(){
           this.showNav = !this.showNav;
      }
  }
}
</script>

<style>
    .nav{
        width: 250px;
    }
    .flex-column .nav-item{
        border-top: 1px solid black;
    }
    .nav-link{
        padding-right: 13.5px;
    }
    .nav-link img{
        float:right;
        margin-left: 10px;
    }
    .flex-column{
        margin-top: 20px;
    }
    .left__nav{
        top: 0;
        left: 0;
        float:left;
        width: 250px;
        height: 100vh;
        transition: 0.3s;
        -webkit-box-shadow: 0px 0px 24px -8px rgba(50, 50, 50, 1);
        -moz-box-shadow:    0px 0px 24px -8px rgba(50, 50, 50, 1);
        box-shadow:         0px 0px 24px -8px rgba(50, 50, 50, 1);
    }
    .show{
        margin-left:0px; 
    }

    .hide{
        margin-left:-200px;
    }

/*Burger menu*/

.hamburger {
    margin-top:20px;
    display: flex;
    align-items: center;
    cursor: pointer;
}

.hamburger__item {
    position: relative;
    width: 25px;
    height: 3px;
    background-color: black;
    transition: 0.3s;
}

.hamburger__item:before,
.hamburger__item:after {
    content: '';
    position: absolute;
    width: 25px;
    height: 3px;
    background-color: black;
}

.hamburger__item:before {
  top: -7px;
  transition: 0.3s;
}

.hamburger__item:after {
  bottom: -7px;
  transition: 0.3s;
}

.hamburger__item_active {
  background-color: transparent !important; /* 1 */
  transition: 0.3s;
}

.hamburger__item_active:before {
  top: 0;
  background-color: #6b25fc;
  transform: rotate(45deg);
  
}

.hamburger__item_active:after {
  bottom: 0;
  background-color: #6b25fc;
  transform: rotate(-45deg);
}

</style>
