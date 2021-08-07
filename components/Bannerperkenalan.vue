<!-- Please remove this file from your project -->
<template>
  <div class="row mx-2 mb-5">
    <div class="col-7 bg-white p4">
      <h1 class="warna-keempat fw-bold">{{data.nama}} <span class="warna-primary">{{data.pekerjaan}}</span></h1>
      <h6 class="warna-ketiga fw-bold" style="line-height:1.5">{{data.deskripsi}}</h6>
      <div :class="data.btn.class"><button class="button-kuning p-2">{{data.btn.value}}</button></div>
    </div>
    <div class="col-5 bg-white pe-0">
      <img :src="data.img_user" class="gambar" alt="user">
    </div>
  </div>
</template>
<script>
  export default {
    props: ["data"]
  }

</script>
<style lang="scss" scoped>
  .p4 {
    padding: 4rem !important;
  }

  .gambar {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

</style>
