<template>
  <div class="mian">
    <!-- <router-view></router-view> -->
    <ul>
      <li v-for="(item,index) in list" :key="index" @click="fn(item,index)" 
      :class="{active:item.donw=='down'&& flag==index,red:item.donw=='up' && flag==index}">one{{index}} </li>
    
    </ul>
    <Home v-show="false"/>
  </div>
</template>

<script>
// import Home from './components/HelloWorld.vue'
export default {
  data(){
    return{
      flag:0,
      list:[
        {donw:'down'},
        {donw:''},
        {donw:''},
      ]
    }
  },
  methods:{
      fn(e,val){
      this.flag=val;
      e.donw=='down'?e.donw='up':e.donw='down';
     }
  },
  //  
components:{
  Home:()=>import('./components/HelloWorld.vue')
}
}
</script>

<style>
 ul>li:hover{
        background-color:blue;
      }
      ul>li.red{
        background-color:red;
      }
      ul>li.color{
         background-color: yellow;
      }
      ul>li.active{
        background-color:blue;
      }
      
      ul>li{
        list-style: none;
        width: 60px;
        height: 20px;
        background-color:lightblue;
        float:left;
        text-align: center;
        line-height: 20px;
        cursor: pointer;
      }
     
      ul>li+li{
        margin-left: 10px;
      }
      
     
</style>
