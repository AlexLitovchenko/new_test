
<template>
  <div >
    <form class="form"> 
      <label> Departure </label>
      <select v-model="selectedDeparture">
        <option v-for="city in UniqCity0" :key="city.city1" v-bind:value="city">{{city}}</option>
        </select>
        
        <p></p>
      <label> Arrival </label>
      <select v-model="selectedArrival"> 
        <option v-for="city_2 in UniqCity" :key="city_2.city2" v-bind:value="city_2">{{city_2}}</option>
        </select>
     
        <p></p>
    <label for="inputDate">Date of Departure</label>
    <p></p>
    <input type="date" class="form-control">
   
    </form>
  </div>
</template>

<script >
import uniq from 'lodash/uniq'

export default {
  name: "Form",
 data:function(){
    return{
      Departure:[
          { city1:'Moscow',
            city2:'Sochi',
            dayDeparture: 22112021,
            timeDeparture:1010,
            timeArrival:2010,
            cost: 100
          },
          { city1:'Moscow',
            city2:'Anapa',
            dayDeparture: 22112021,
            timeDeparture:1010,
            timeArrival:2010,
            cost: 200
          },
          { city1:'Anapa',
            city2:'Sochi',
            dayDeparture: 22112021,
            timeDeparture:1010,
            timeArrival:2010,
            cost: 50
          },
          { city1:'Sochi',
            city2:'Anapa',
            dayDeparture: 22112021,
            timeDeparture:1010,
            timeArrival:2010,
            cost: 120
          },
          { city1:'Moscow',
            city2:'Kiev',
            dayDeparture: 22112021,
            timeDeparture:1010,
            timeArrival:2010,
            cost: 300
          }
      ],

      selectedDeparture:'',
      selectedArrival:'',
      value: ''
    }
  },
computed: {
  UniqCity () {
    return uniq(this.Departure.map(({ city2 }) => city2))
  },
  UniqCity0(){
    return uniq(this.Departure.map(({city1})=>city1))
  }
}

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

form {

   width: 100%;
      padding: 10px;
      border-radius: 5px;
      background: rgb(170, 229, 227);
      box-shadow: 0 0 8px  #cc7a00; 

}
select{
  width: 100%;
      padding: 8px 8px;
      margin: 8px 0;
      display: inline-block;
      border: 1px solid #ccc;
      box-sizing: border-box;
}
input{
       position: relative;
      margin: 10px 0;
}
label{
     margin: 0 0 20px;
      font-weight: 400;
      color: #751cc9;
   
}


</style>
