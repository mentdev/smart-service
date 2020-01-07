<template>
 <div class="services">
   <h1>ข้อมูลการแจ้งซ่อม</h1>   
   
   <v-container class="grey lighten-5" >

     <v-layout row class="mb-5" no-gutters>
       <v-tooltip top>
         <template v-slot:activator="{ on }">
          <v-btn small text color="grey" @click="sortBy('buildingName')" v-on="on">
            <v-icon left small>mdi-folder</v-icon>
            <span class="caption text-lowercase">By buildingName</span>
          </v-btn>          
         </template>
         <span>Sort by Building Name</span>
       </v-tooltip>

      <v-tooltip top>
        <template v-slot:activator="{ on }">
          <v-btn small text color="grey" @click="sortBy('roomName')" v-on="on">
            <v-icon left small>mdi-broom</v-icon>
            <span class="caption text-lowercase">By roomName</span>
          </v-btn>
        </template>
         <span>Sort by Room Name </span>
      </v-tooltip>

     </v-layout>


     
     <v-card flat v-for="service in services" :key="service.buildingName">
       <v-layout row wrap :class="`pa-3 service status${service.serviceStatusID}`" no-gutters>
        <v-flex xs12 md6>
          <div class="caption grey--text">อาคาร</div>
          <div>{{ service.buildingName }}</div>
        </v-flex>
        <v-flex xs6 sm4 md2>
          <div class="caption grey--text">ชั้น</div>
          <div>{{ service.floorName }}</div>
        </v-flex>
        <v-flex xs6 sm4 md2>
          <div class="caption grey--text">ห้อง</div>
          <div>{{ service.roomName}}</div>
        </v-flex>
        <v-flex xs6 sm4 md2>
          <div class="caption grey--text">ผู้ติดต่อ</div>
          <div>{{ service.contact }}</div>
        </v-flex>
       </v-layout>
       <v-divider></v-divider>
     </v-card>

   </v-container>
 </div> 
</template>

<script>
  export default{
    data(){
      return{
        services: [
          { buildingName: 'อาคารสำนักงานอธิการบดี', floorName: '1', roomName: 'บริหาร105/13', contact: 'สมชาย', serviceStatusID: 1},
          { buildingName: 'อาคารเรียนและปฏิบัติการด้านภาษา ( ICT )', floorName: '3', roomName: 'ห้องคอมพิวเตอร์ ICT1102', contact: 'สมคิด', serviceStatusID: 1},
          { buildingName: 'อาคารสำนักงานอธิการบดี2', floorName: '1', roomName: 'บริหาร105/1', contact: 'สวัสดี', serviceStatusID: 2},
          { buildingName: 'โรงอาหาร 2', floorName: '1', roomName: 'โรงอาหาร 2', contact: '...', serviceStatusID: 0}
        ]
      }
    },
    methods: {
      sortBy(prop){
        this.services.sort((a,b) => a[prop] < b[prop] ? -1 : 1);
      }
    }
  }
</script>
<style>
.service.status0 {
  border-left: 4px solid #33ccdd;
}
.service.status1 {
  border-left: 4px solid orange;
}
.service.status2 {
  border-left: 4px solid tomato;
}
</style>

