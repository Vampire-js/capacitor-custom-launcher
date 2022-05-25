<template>
<div class="h-[100vh]" style="background:var(--primary);">
          
          <div class="main p-4" style="height:calc(100vh - 80px);">
          
          
          
          
          <SearchWidget/>
          
          
          
          
          
          </div>

          <div class="w-screen flex justify-center"><div @click="open" class="h-16 w-16 flex justify-center rounded-full items-center " style="background:rgba(0,0,0,0.023)"><ion-icon name="apps" class="text-4xl" style="color:var(--secondary);" /></div></div>
    <div class="w-screen h-screen absolute " style="background:var(--secondary);" :style="{top:`${topVal}%` , transition:'0.6s ease'}" ref="drawer"  >
<div class="toggle h-[100px]  flex items-center pt-6" style="background:rgba(0, 0, 10, 0.08);">
    <div class="flex items-center justify-center w-full">
  
  <label for="toggleB" class="flex items-center cursor-pointer">
    <!-- toggle -->
    <div class="warm mr-4 font-bold text-white px-2 py-1 rounded" style="background:#FF6363;">Warm</div>
    <div class="relative">
      <!-- input -->
      <input type="checkbox" id="toggleB" v-model="isToggled" @change="changeTheme" class="sr-only">
      <!-- line -->
      <div class="block w-14 h-8 rounded-full" style="background:var(--primary);"></div>
      <!-- dot -->
      <div class="dot absolute left-1 top-1  w-6 h-6 rounded-full transition" style="background:white;"></div>
    </div>
   <div class="warm ml-4 font-bold text-white px-2 py-1 rounded" style="background:#79DAE8;">Cold</div>

  </label>

</div>
</div>
 
<div class="apps" style="height:calc(100vh - 160px);">
 

 </div>
 <div class="head h-100   flex" style="background:var(--secondary);">
           <div @click="close" class=" animate-bounce w-screen p-2 flex items-center justify-center text-[var(--primary)] font-extrabold" style="color:var(--primary);"><ion-icon name="arrow-down" class="text-2xl mr-4 " style="color:var(--primary);" /> Tap to close</div>
    </div>
    </div>
    </div>
</template>

<script setup> 
import {ref} from 'vue'
import MoreAppsWidget from './widgets/MoreAppsWidget.vue'
import SearchWidget from './widgets/SearchWidget.vue'
import { StatusBar  , Style} from '@capacitor/status-bar'


const topVal = ref(100);
const isToggled = ref(false)
function open(){
topVal.value = 0
}

function close(){
    topVal.value = 100
}

const changeTheme = () => {
if(isToggled.value == true){
document.querySelector(':root').style.setProperty('--primary', '#213E3B');
document.querySelector(':root').style.setProperty('--secondary', '#A6F6F1');
document.querySelector(':root').style.setProperty('--tertiary', '#1e3835');
StatusBar.setStyle({ style: Style.Dark });

}else{
    document.querySelector(':root').style.setProperty('--primary', '#FF6363');
document.querySelector(':root').style.setProperty('--secondary', '#FFAB76');
document.querySelector(':root').style.setProperty('--tertiary', '#FC4F4F');
StatusBar.setStyle({ style: Style.Dark });
}

};
</script>


<style>
input:checked ~ .dot {
  transform: translateX(100%);
  background-color: #48bb78;
  transition:0.3s ease;
}
</style>