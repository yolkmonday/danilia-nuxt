<template>
  <div>
    <section v-if="page==='satu'" class="h-screen p-8 bg-maroon">
      <div class="w-full bg-white rounded-lg h-full flex flex-col">
        <div class="h-1/4"></div>
        <div>
        <img class="w-28 m-auto animate__animated animate__fadeInUp" src="~/assets/logo.svg" alt="">
        </div>

        <div class="mt-12">
          <p class="w-full text-center text-xs text-gray-500 animate__animated animate__fadeInUp">Kepada Yth.<br> Bapak/Ibu/Saudara/i</p>
          <h1 class="capitalize text-xl text-center font-bold mt-4 animate__animated animate__fadeInUp">{{name}}</h1>
        </div>
        <div class="flex w-full mt-12">
          <button class="animate__animated animate__fadeInUp mx-auto bg-maroon rounded-full p-3" @click.prevent="open">
            <svg xmlns="http://www.w3.org/2000/svg" fill="#fff" width="24" height="24" viewBox="0 0 24 24"><path d="M.026 24l11.974-11.607 11.974 11.607h-23.948zm11.964-23.961l-11.99 8.725v12.476l7.352-7.127-5.653-4.113 10.291-7.488 10.309 7.488-5.655 4.108 7.356 7.132v-12.476l-12.01-8.725z"/></svg>
          </button>
        </div>
        <!-- <div class="fixed bottom-0 w-full px-4 mb-4 -ml-4 ">
          <div class="border text-white border-gold p-4 rounded-xl text-center">
            <span class="text-xs">Kepada Yth.</span>
            <span class="text-xs block">Bapak / Ibu / Saudara / i</span>
            <span class="capitalize">{{name}}</span>
          </div>
          <div class="w-full mt-4">
            <button class="w-full bg-gold py-4 rounded-xl" @click.prevent="open">Buka Undangan</button>
          </div>
         
        </div> -->
      </div>
    
    
    </section>
    <div v-if="page==='dua'" style="background:url('/02.jpg')" >
       <section class="min-h-screen flex items-center px-4" >
     <div class="flex flex-col items-center w-full">
       <h1 class="block text-center w-full text-gold mb-8 animate__animated animate__fadeInUp">THE WEDDING OF</h1><br>
     <img class="w-32 mx-auto animate__animated animate__fadeInUp" src="~/assets/logo.svg" alt="">
       <p class="mt-10 animate__animated text-gold animate__fadeInUp" >PEKANBARU, 31 JULI 2021</p>
     
     </div>
   </section>

   <section  class="min-h-screen flex items-center">
     <div>
 <p class="px-4 text-white text-sm text-center">
       “Dan di antara tanda-tanda kekuasaan-Nya ialah Dia menciptakan untukmu isteri-isteri dari jenismu sendiri, supaya kamu cenderung dan merasa tenteram kepadanya, dan dijadikan-Nya diantaramu rasa kasih dan sayang. Sesungguhnya pada yang demikian itu benar-benar terdapat tanda-tanda bagi kaum yang berfikir.”
     </p>
     <p class="text-center text-md text-white font-bold mt-3">( Qs. Ar-Ruum : 21)</p>
     </div>
    
   </section>

   <section  class="min-h-screen flex items-center">
     <div>
 <p class="text-center text-sm">Bismillahirrahmanirrahim</p>
     <p class="text-center text-sm">Assalamu’alaikum Warahmatullahi Wabarakatuh</p>
     <p class="text-center text-sm">Dengan memohon Rahmat dan Ridha Allah SWT, kami bermaksud
menyelenggarakan Resepsi pernikahan putra-putri kami</p>
<div class="py-8">
<h3 class="block text-3xl text-center gold">
  Hamdani Asril, S.Kom
</h3>
<p class="text-center text-sm">Putra dari Bapak Drs. H. Asril, M.H. & Ibu Dra. Erina, M.H. </p>
<p class="text-center gold text-3xl py-4">&</p>
<h3 class="block text-3xl text-center gold">
  Suliatun, S.Kom
</h3>
<p class="text-center text-sm">Putri dari Bapak Sulaiman (alm) & Ibu Suliyah</p>
</div>
     </div>
    

   </section>

   <section  class="flex items-center min-h-screen">
     <div class="w-full text-center">
  <h3>Waktu dan Tempat</h3>
     <div class="grid grid-cols-2 gap-4">
       <div class="flex flex-col rounded-lg border p-3">
         <span class="block border-b">Akad</span>
         <span class="text-lg font-bold text-white">Kamis<br>29 Juli 2021</span>
         <span>Jl. Sawit IV (Jlr.8), Sp. 1<br> Desa Hangtuah, Perhentian Raja</span>
       </div>
       <div class="flex flex-col rounded-lg border p-3">
         <span class="block">Resepsi</span>
         <span class="text-lg font-bold text-white">Sabtu<br>31 Juli 2021</span>
         <span>Jl. Melati Perum Athaya2 Blok A3<br>Panam, Pekanbaru</span>
       </div>
      
     </div>
   
     </div>
   </section>
    </div>
    


  </div>
</template>

<script>
export default {
  data() {
    return {
      page: 'satu'
    }
  },
  computed: {
    name() {
     const n = this.$route.params.slug
     return n.replace('-', ' ')
    }
  },
  methods: {
    open() {
      this.page = 'dua'
      const audio = new Audio('/therain.mp3');
      audio.play();
    }
  }
}
</script>

<style>
@import url('https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css');
</style>
