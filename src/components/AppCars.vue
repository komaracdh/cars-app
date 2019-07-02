<template>
    <div>
        <ul>
            <li v-for='(car,index) in cars' :key="index">
                {{car.brand}} - {{car.model}}
       
            </li>
        </ul>
        
    </div>
</template>

<script>
import { carsService } from '@/services/CarsServices'

export default {
    date() {
        return {
            cars:[],
        }
    },
      created () {
         
     carsService.getAll()
       .then(response => {
           console.log(response);
           
         this.cars = response.data
       }).catch(e => {
         console.log(e)
       })


      
  }


}
</script>

<style>

</style>
