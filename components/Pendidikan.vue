<!-- Please remove this file from your project -->
<template>
  <div class="row mx-2 mb-5">
    <div class="col-12 mb-5">
      <h3 class="fw-bold text-center">{{data.judul}}</h3>
    </div>
    <div class="col-12 bg-white" v-for="(i,index) in data.details" :key="index">
      <div class="row bg-white p-5">
        <div class="col-5">
          <h5 class="mb-4">{{i.judulkiri}}</h5>
          <h6 class="warna-ketiga">{{i.deskripsikiri}}<span class="utama ms-5 p-2 text-white">{{i.sampai}}</span></h6>
        </div>
        <div class="col-7">
          <h5 class="mb-4">{{i.judulkanan}}</h5>
          <h6 class="warna-ketiga" style="line-height:1.5">{{i.deskripsikanan}}</h6>
        </div>
      </div>
      <hr class="mt-0" v-if="index !== data.details.length-1">
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
