<template>
  <div>
    <section v-if="page==='satu'" class="h-screen p-8" style="background: url('bg-1.png');max-width:768px;margin:auto;" >
      <div class="w-full bg-white rounded-lg h-full flex flex-col">
        <div class="h-1/4"></div>
        <div>
          <p class="text-maroon text-center mb-8 text-sm">THE WEDDING OF</p>
        <img class="w-28 m-auto animate__animated animate__fadeInUp" src="~/assets/logo.svg" alt="">
        </div>

        <div class="mt-12">
          <p class="w-full text-center text-xs text-maroon animate__animated animate__fadeInUp">Kepada Yth.<br> Bapak/Ibu/Saudara/i</p>
          <h1 class="capitalize text-xl text-center text-maroon font-bold mt-4 animate__animated animate__fadeInUp">{{name}}</h1>
        </div>
        <div class="flex w-full mt-12">
          <button class="animate__animated animate__fadeInUp mx-auto bg-maroon rounded-full p-3" @click.prevent="open">
            <svg xmlns="http://www.w3.org/2000/svg" fill="#fff" width="24" height="24" viewBox="0 0 24 24"><path d="M.026 24l11.974-11.607 11.974 11.607h-23.948zm11.964-23.961l-11.99 8.725v12.476l7.352-7.127-5.653-4.113 10.291-7.488 10.309 7.488-5.655 4.108 7.356 7.132v-12.476l-12.01-8.725z"/></svg>
          </button>
        </div>
     
      </div>
    
    
    </section>
    <div v-if="page==='dua'">
       <index/>
    </div>
    


  </div>
</template>

<script>
import Countdown from 'vuejs-countdown'
import Index from './index.vue'
export default {
  components: { Countdown, Index },
  data() {
    return {
      page: 'satu'
    }
  },
  computed: {
    name() {
     const n = this.$route.params.slug
     return n.split('-').join(' ')
    }
  },
  methods: {
    open() {
      this.page = 'dua'
      const audio = new Audio('/therain.mp3');
      audio.play();
    },
    gmaps() {
      window.open('https://goo.gl/maps/nem6wyrpojMw2a5p7', '_blank')
    }
  }
}
</script>

<style>
@import url('https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css');
@import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');
body {
  font-family: 'Poppins' !important;
}
</style>
