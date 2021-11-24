<template>
    <div class="Ticket">
    
    <table >
      <caption>Tickets</caption>
      <tr>
        <th >DepartureCity</th>
        <th>ArrivalCiyt</th>
        <th>DayOfDeparture</th>
        <th>TimeOfDeparture</th>
        <th>TimeOfArrival</th>
        <th  @click="sortBy='cost'">Cost</th>
      </tr>
      <tr v-for="departure in DepartureSorted" :key="departure.city1">
        <td>{{departure.city1}}</td>
        <td>{{departure.city2}}</td>
        <td>{{departure.dayDeparture}}</td>
        <td>{{departure.timeDeparture}}</td>
        <td>{{departure.timeArrival}}</td>
        <td>{{departure.cost}}</td>
      </tr>
    </table>
    </div>
</template>

<script>



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
      value: '',
      sortBy: null,
    }
  
  },
  computed : {
  DepartureSorted () {
    const sortBy = this.sortBy
    if (!sortBy) return this.Departure
    return this.Departure.sort((a,b)=> a[sortBy] > b[sortBy] ? 1 : -1)
  }

}
}
</script>
<style scoped>
table
{ 
     width: 300px; /* Ширина таблицы */
    border: 1px solid green; /* Рамка вокруг таблицы */
    margin: auto;
      color: #751cc9;
} 
</style>