<!-- Please remove this file from your project -->
<template>
  <div class="row mx-2 mb-5">
    <div class="col-12 mb-5">
      <h3 class="fw-bold text-center">{{data.judul}}</h3>
    </div>
    <div class="col-4 ps-2 pe-2 mb-3" v-for="(i,index) in data.details" :key="index">
      <div class="card">
        <a :href="i.url">
          <img :src="i.img" class="card-img-top" :alt="i.url">
        </a>
      </div>
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
