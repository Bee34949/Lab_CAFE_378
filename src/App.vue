<script setup>
import { ref } from 'vue';
const travellist = ref ([
  {name:'ท่าช้าง', price:80, size:{s: 80,m: 150, l: 200}, img:"https://p-u.popcdn.net/event_details/posters/000/008/856/original/cfe1b94d03c5137faf1500f98117421e9f2ac9db.jpg?1590662796"},
  {name:'GoodView', price:120, size:{s: 120,m: 180, l: 250}, img:"https://th.bing.com/th/id/OIP.R9A5Gpn-DpOChTHyuic_sAHaFj?pid=ImgDet&rs=1"},
  {name:'RiverSide' , price:150, size:{s: 150,m: 190, l: 300}, img:"https://th.bing.com/th/id/R.ab9802205edc889cdc62f84af245316c?rik=EUFmNFFfO91eJA&riu=http%3a%2f%2fwww.dooasia.com%2fwp-content%2fuploads%2f2018%2f05%2fThe-RiverSide-%e0%b9%80%e0%b8%8a%e0%b8%b5%e0%b8%a2%e0%b8%87%e0%b9%83%e0%b8%ab%e0%b8%a1%e0%b9%88-7-696x464.jpg&ehk=IfTrEAF8BEuE9hJhtMKHQNYZmV%2boSJEesY%2fzQmFNYoo%3d&risl=&pid=ImgRaw&r=0"},
  {name:'WarmUp', price:100, size:{s: 100,m: 200, l: 500}, img:"https://d136usn7jnoe61.cloudfront.net/pictures/21526/s2n_0002_p1d06tc4oou8jlkvr0l1mag1grj6.jpg"},
  {name:'ตะวันแดง', price:90, size:{s: 90,m: 250, l: 700}, img:"https://th.bing.com/th/id/R.6fd3de7109e6a325c0d72efb53de2050?rik=Aa1zQxZXAWtxSg&riu=http%3a%2f%2ftawandang.com%2fwp-content%2fuploads%2f2017%2f08%2fTWDjang-Chaeng-Wattana.jpg&ehk=WHcn32JlAx8ZTvDdAHwMb81EWoU%2fiVLDtNNd6K%2bP6Ao%3d&risl=&pid=ImgRaw&r=0"},
]);
//เก็บข้อมูลการจองร้าน
const bookinglist = ref([]);
//function
function booking(name) {
  if (!bookinglist.value.includes(name)) {
    bookinglist.value.push(name);
  }
}
</script>

<template>
  <div class="p-3 m-0 border-0 bd-example m-0 border-0">
    
    <div class="text-center">
      <div class="row row-cols-1 row-cols-md-3 g-4">
        <div class="col" v-for="(i,name) in travellist" :key="index">
          <div class="card text-bg-dark h-100" style="width:18rem">
          <img v-if="i.img" :src="i.img" class="card-img-top" alt="..." />
          <div class="card-body">
          <h5 class="card-title">{{ i.name }}</h5>
          <p class="card-text"> 
            จำนวนโต๊ะที่จอง <input type="number" >
            ชื่อ <input type="text">
            เบอร์โทร <input type="number">
            วันที่ เวลา <input type="datetime">
            
          </p>
           
          <a class="btn btn-primary" @click="booking(i.name)">จองโต๊ะ</a>
          
        </div>
          </div>

        </div>

      </div>
    </div>
  </div>
  
  <table class="table table-sm table-dark" v-if="bookinglist.length > 0">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">รายชื่อร้านที่จอง</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="(item, index) in bookinglist " :key="index">
      <th scope="row">{{ index+1 }}</th>
      <td>{{ item }}</td>
    </tr>
  </tbody>
</table>
<table class="table table-dark table-striped">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">รายชื่อร้านที่จอง</th>
     
    </tr>
  </thead>
  <tbody>
   
    <tr v-for="(item,index)  in bookinglist"  :key="index">
      <th scope="row">{{ index+1 }}</th>
    <td>{{ item }}</td>
    </tr>
    <tr>
      
      
    </tr>
    <tr>
      
      
      
    </tr>
  </tbody>
</table>
</template>


