<!-- eslint-disable quotes -->
<template>

   <div class="py-4">
    <div class="shadow-lg group container  rounded-md  max-w-sm flex justify-center items-center  mx-auto ">
        <div class="py-8 px-4   rounded-b-md fd-cl group-hover:opacity-25">
            <span class="block text-lg text-gray-800 font-bold tracking-wide">{{proName.slice(1,10)}}</span>
            <span  class="block text-gray-600 text-sm">{{proDesc}}
            </span>
        </div>
 <div class="absolute opacity-0 fd-sh group-hover:opacity-100">
       <span class="text-3xl font-bold text-white tracking-wider leading-relaxed font-sans">{{proName.slice(1,12)}}</span>
       <div class="pt-8 text-center">
           <button class="text-center rounded-lg p-4 bg-white  text-gray-700 font-bold text-lg">Learn more</button>
           </div>
    </div>
</div>
</div>
</template>
<script lang="ts">
// eslint-disable-next-line quotes
import { Component, Prop, Vue } from "vue-property-decorator"

@Component
export default class CardPro extends Vue {
  @Prop() public proName!: string;
  @Prop() public proUrl!: string;
  @Prop() public proDesc!: string;
}
</script>
