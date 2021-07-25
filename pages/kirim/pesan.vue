<template>
    <div>
        <form @submit.prevent="goto()">
        <input v-model="nama" type="text" class="w-full py-3 border px-4" placeholder="nama undangan">
        <input v-model="nomor" type="number" class="w-full py-3 border px-4" placeholder="nomor format 62853xxxxx">
        <textarea v-model="pesan" class="w-full py-3 border px-4" placeholder="pesan"/>
        <button class="border">Kirim</button>
        </form>
    </div>
</template>

<script>
export default {
    data() {
        return {
            nama:'',
            nomor: '',
            pesan: ''
        }
    },
    methods: {
        goto() {
            const pesan = `${this.pesan} - danilia.online/${this.nama.split(' ').join('-')}`
             window.location.href = `https://api.whatsapp.com/send?phone=${this.nomor}&text=${pesan}`
        }
    }
}
</script>