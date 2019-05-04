<template>
  <div id="main">
      <div class="row">
        <div class="col-4 ">
          <div class="card">
            <div class="card-body">
              <h5 class="card-title">Дата</h5>
              <p class="card-text time">{{now}}</p>
            </div>
          </div>
        </div>
        <div class="col-4">
          <div class="card">
            <div class="card-body">
              <h5 class="card-title">Погода</h5>
              <p class="card-text time"> <img :src="weatherImg"> {{weatherTemp}}</p>
            </div>
          </div>
        </div>
        <div class="col-4">
          <div class="card">
            <div class="card-body">
              <h5 class="card-title">Дата</h5>
              <p class="card-text time">{{now}}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
import api from '@/components/api/getInfo.vue';
export default {
  name: 'HelloWorld',
  data () {
    return {
      now: 'none',
      weatherImg: 'none',
      weatherTemp: 'none',

    }
  },
  methods:{
    getDate: function(){
      var date = new Date();
      this.now = date.toLocaleTimeString() + ' | ' +  date.toLocaleDateString();
      setTimeout(this.getDate,1);
    },

    getWeather: function(){
      var city = 'Novosibirsk';
      var location;
      api.getRequest('https://api.apixu.com/v1/current.json?key=4d16eff399e14a1f872133912190405&q='+city).then((data) => {
        this.weatherTemp = data.current.temp_c;
        this.weatherImg = data.current.condition.icon;
      });
    }

  },
  created: function(){
    this.getDate();
    this.getWeather();
  }
  

}
</script>

<style>
  .card{
    height: 120px;
  }
  .card-title{
    text-align: center;
  }
  .time{
    text-align: center;
    font-size: 20px;
  }
</style>
