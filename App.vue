<script>
import NavBtnMB from './components/NavBtnMB.vue'

import logo from '@/assets/images/logo.svg?url'
import navToOpen from '@/assets/images/icon-hamburger.svg?url'
import navToClose from '@/assets/images/icon-close.svg?url'

export default {
   data() {
      return {
         logo,
         navToOpen,
         navToClose,
         devicesImg: 'bg-[url(@/assets/images/illustration-devices.svg?url)]',
         isNavOpen: false,
      }
   },
   components: {
      NavBtnMB,
   }
}
</script>
<template>
   <body class=" relative flex flex-col gap-[60px] DT:gap-32 overflow-hidden">
      <nav
         class=" relative flex justify-between items-center w-full max-w-[425px] DT:max-w-[1920px] px-8 DT:px-[165px] pt-9 DT:pt-16 select-none z-20">
         <img class=" h-6 DT:h-8" :src="logo" alt="logo" draggable="false">
         <div @click="isNavOpen = !isNavOpen" class=" DT:hidden cursor-pointer">
            <img v-show="isNavOpen == false" :src="navToOpen" alt="navBarValue" draggable="false">
            <img v-show="isNavOpen == true" :src="navToClose" alt="navBarValue" draggable="false">
         </div>
         <!-- Nav Mobile -->
         <div v-show="isNavOpen == true"
            class=" absolute right-0 top-[100px] flex DT:hidden flex-col items-center gap-6 w-[311px] mx-8 px-6 py-6 bg-white rounded-[3px]">
            <NavBtnMB btn-text="Product" />
            <NavBtnMB btn-text="Features" />
            <NavBtnMB btn-text="Pricing" />
            <div class=" w-full h-[1px] bg-neo-very-dark-blue bg-opacity-[.15]"></div>
            <NavBtnMB btn-text="Login" :is-opaque="true" />
         </div>
         <!-- Nav Desktop -->
         <div class=" hidden DT:flex gap-12 text-neo-very-dark-blue">
            <div class=" flex items-center gap-10">
               <NavBtnMB btn-text="Product" />
               <NavBtnMB btn-text="Features" />
               <NavBtnMB btn-text="Pricing" />
               <div class=" w-[6px] h-[6px] bg-neo-very-dark-blue bg-opacity-[.15] rounded-full"></div>
            </div>
            <NavBtnMB btn-text="Login" :is-opaque="true" />
         </div>
      </nav>
      <main
         class=" flex flex-col DT:flex-row-reverse DT:justify-end gap-[87px] DT:gap-0 w-full max-w-[425px] DT:max-w-[1920px] pb-[92px] DT:pb-[125px]">
         <div
            class=" absolute -right-[132px] DT:right-0 top-0 w-[319px] DT:w-[705px] h-[425px] DT:h-[427px] bg-neo-light-grayish-blue rounded-es-[60px]">
         </div>
         <div
            :class="` relative left-[10px] DT:left-[124px] DT:w-[916px] h-[243px] DT:h-[455px] ${devicesImg} bg-cover z-10`">
         </div>
         <div
            class=" flex flex-col gap-7 DT:gap-16 mt-10 px-8 DT:px-0 DT:pl-[165px] text-neo-very-dark-blue font-barlow-condensed uppercase">
            <div class=" flex flex-col gap-4 DT:gap-5 DT:w-[470px]">
               <div class=" flex items-center gap-4 text-[15px]">
                  <h3
                     class=" flex justify-center items-center w-[48px] h-[25px] bg-neo-very-dark-blue text-white tracking-[1px] font-bold rounded-[12.5px]">
                     New
                  </h3>
                  <h4 class=" opacity-50 tracking-[5px]">
                     Monograph Dashboard
                  </h4>
               </div>
               <h1 class=" DT:mb-3 text-[40px] DT:text-[64px] leading-[40px] DT:leading-[64px] font-bold ">Powerful
                  insights into
                  your team</h1>
               <p class=" opacity-75 font-barlow normal-case">
                  Project planning and time tracking for agile teams
               </p>
            </div>
            <div class=" flex gap-5 DT:gap-6 items-center text-[14px] DT:text-[15px] leading-[17px] DT:leading-[18px]">
               <button
                  class=" w-[153px] h-[40px] bg-neo-red hover:bg-opacity-75 rounded-[5px] text-white DT:text-[16px] leading-[19px] tracking-[.93px] font-bold uppercase select-none">
                  Schedule a demo
               </button>
               <h3 class=" opacity-50 tracking-[2.5px] DT:tracking-[5px]">
                  to see a preview
               </h3>
            </div>
         </div>
      </main>
   </body>
</template>