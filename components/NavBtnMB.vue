<script>
export default {
   data() {
      return {

      }
   },
   props: {
      btnText: {
         String,
         default: 'empty',
      },
      isOpaque: {
         Boolean,
         default: false,
      }
   },
   computed: {
      opaqueState() {
         return this.isOpaque ? 'opacity-50' : 'opacity-100';
      }
   }
}
</script>
<template>
   <button
      :class="` ${opaqueState} text-[18px] leading-[22px] tracking-[1.2px] font-bold font-barlow-condensed uppercase hover:underline underline-offset-2`">
      {{ btnText }}
   </button>
</template>