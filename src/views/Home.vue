<template>
<div> <h1 class="text-red-700 font-bold text-3xl text-center m-5">List Of Posts</h1>
  <div class="container flex justify-center flex-wrap mt-3">
    <div
      v-for="proj in projs"
      :key="proj.proName"
      class="content-div m-1 py-1 px-1 flex rounded-md bg-red-400 shadow-lg lg:w-1/4 md:w-1/3 sm:w-full sm:flex-nowrap w-full p-2 hover:bg-red-300 "
    >
      <CardPro
        class=" "
        :proName="proj.proName"
        :proDesc="proj.proDesc"
        :proUrl="proj.proUrl"
      />
    </div>
  </div></div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import axios from 'axios'
import CardPro from '@/components/CardPro.vue'

interface Repo {
  proName: string;
  proUrl: string;
  proDesc: string;
}
@Component({
  components: { CardPro }
})
export default class Home extends Vue {
  projs: Repo[] = [];
  mounted () {
    axios
      .get('https://jsonplaceholder.typicode.com/posts')
      .then((values) => {
        values.data.forEach((proj: any) => {
          this.projs.push({
            proName: proj.title,
            proDesc: proj.body,
            proUrl: proj.html_url
          })
        })
      })
      .catch(console.error)
  }
}
</script>
<style>
  .content-div{

  background-repeat: no-repeat;
  background-size: cover;
  background-position:center;
}
  .content-div:hover{
    background:
    linear-gradient(to right,
     rgba(239, 2, 26, 0.801), hsla(0, 51%, 75%, 0.801) )
    }

    .image-cover  {
      height:260px;
    }
  /*
  -remove the classes below if you have the 'group-hover'property added in your tailwind config file
  -also remove the class from the html template
  */
    .content-div:hover .fd-cl{
 opacity: 0.25;
    }
    .content-div:hover .fd-sh{
 opacity: 1;
    }
</style>
<!--some hover in tail hover:opacity-25 -->
