<script setup>
import { ref } from 'vue'
import { RouterLink, RouterView } from 'vue-router'
import MenuItem from './components/MenuItem.vue'

import ChevronUp from 'vue-material-design-icons/ChevronUp.vue';
import ChevronDown from 'vue-material-design-icons/ChevronDown.vue';
import ChevronRight from 'vue-material-design-icons/ChevronRight.vue';
import ChevronLeft from 'vue-material-design-icons/ChevronLeft.vue';

let openMenu = ref(false)
</script>

<template>
  <div>
    <div
    class="
    w-[calc(100%-240px)]
    h-[60px]
    fixed
    right-0
    z-20
    bg-[#101010]
    bg-opacity-80
    flex
    items-center
    justify-between
    "
  >
  <div class="flex item-center ml-6">
    <button type="button" class="rounded-full bg-black p-[1px] cursor-pointer">
      <ChevronLeft fillColor="#FFFFFF" :size="30" />
    </button>
    <button type="button" class="rounded-full bg-black p-[1px] ml-4 cursor-pointer">
      <ChevronRight fillColor="#FFFFFF" :size="30" />
    </button>
  </div>

  <button 
  @click="openMenu = !openMenu"
  :class="openMenu ? 'bg-[#282828]' : 'bg-black'"
  class="bg-black hover:bg-[#282828] rounded-full p-0.5 mr-8 mt-0.5 cursor-pointer"
>
  <div class="flex items-center">
    <img
      class="rounded-full"
      width="27"
      src="https://media.licdn.com/dms/image/D4E35AQHS67vcenVNZg/profile-framedphoto-shrink_200_200/0/1687546996711?e=1699286400&v=beta&t=jC5ovAwVCvrKaSTgyOslcTR8g2bM9Vi5eVsWm4rjl4I"
    >
    <div class="text-white text-[14px] ml-1.5 font-semibold">Sergi Linuesa</div>
    <ChevronDown v-if="!openMenu" fillColor="#FFFFFF" :size="25" />
    <ChevronUp v-if="openMenu" fillColor="#FFFFFF" :size="25" />
  </div>
</button>

<span
v-if="openMenu"
   class="fixed w-[190px] bg-[#282828] shadow-2xl z-50 rounded-sm top-[52px] right-[35px] p-1 cursor-pointer"
>
<ul class="text-gray-200 font-semibold text-[14px]">
  <li class="px-3 py-2.5 hover:bg-[#3E3D3D] border-b border-b-gray-600">Profile</li>
  <li class="px-3 py-2.5 hover.bg-[#3E3D3D]">Log out</li> <!-- Corregido el nombre de la clase -->
</ul>
</span>
    </div>

    <div
    id="SideNaV"
    class="h-[100%] p-6 w-[240px] fixed z-50 bg-black"
    >
      <RouterLink to="/">
        <img width="125" src="/images/icons/spotify-logo.png">
      </RouterLink>
      <div class="my-8">
        <ul>
          <RouterLink to="/">
            <MenuItem class="ml-[1px]" :iconSize="23" name="Home" iconString="home" pageUrl="/"/>
          </RouterLink>
        </ul>
      </div>
    </div>
  </div>
</template>
