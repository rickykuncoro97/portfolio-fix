<!-- Please remove this file from your project -->
<template>
  <div class="row mx-2 mb-5">
    <div class="col-12 mb-5">
      <h3 class="fw-bold text-center">{{data.judul}}</h3>
    </div>
    <div class="col-12 bg-white">
      <form class="row g-3 p-3" @submit="checkForm">
        <div class="col-12" v-for="(value,name,index) in data.form" :key="'input'+index">
          <label class="form-label">{{value.name}}</label>
          <input type="text" v-model="form[value.model]" class="form-control form-control-lg input-custom"
            v-if="value.type ==='text'" required>
          <textarea v-model="form[value.model]" class="form-control form-control-lg input-custom"
            v-else-if="value.type ==='textarea'" rows="6" required></textarea>
        </div>
        <div class="col-5">
          <button class="button-kuning p-2" type="submit">KIRIM</button>
        </div>
      </form>
    </div>
  </div>
</template>
<script>
  import * as config from '../static/data';
  export default {
    props: ["data"],
    data() {
      return {
        config,
        form: this.data.model
      }
    },
    methods: {
      checkForm(e) {
        e.preventDefault();
        const perkenalan = `Halo, nama saya ${this.form.nama ?this.form.nama : 'John Doe'}.`
        let wa =
          `https://api.whatsapp.com/send?phone=${this.config.hp}&text=${perkenalan} ${this.form.msg ? this.form.msg : 'Tidak ada pesan'}. Hubungi Saya jika berminat, ${this.form.hp ?this.form.hp : '0000000'} `
        location.href = wa
      }
    }
  }

</script>
<style lang="scss" scoped>

</style>
