<template>
  <div class="container-fluid bg-utama">
    <link href='https://fonts.googleapis.com/css?family=Ubuntu' rel='stylesheet'>
    <div class="row">
      <div class="col-3 bg-white h-100">
        <div class="p-5">
          <div class="d-flex justify-content-center">
            <img :src="config.menukiri.img_user" class="rounded-circle" alt="user" width="150px" height="150px">
          </div>
          <div class="d-flex justify-content-center">
            <p class="mt-3 h5 tebaldikit mb-3">{{config.menukiri.nama}}</p>
          </div>
          <div class="d-flex h6 justify-content-center">
            <p class="h-0-8 mb-2">{{config.menukiri.profesi}}</p>
          </div>
          <hr class="mt-0 mb-3">
          <div class="d-flex bd-highlight mb-3 font-10pt" aria-label="Umur">
            <div class="me-auto p-2 bd-highlight utama">Umur: </div>
            <div class="p-2 bd-highlight">{{config.menukiri.umur}}</div>
          </div>
          <div class="d-flex bd-highlight mb-3 font-10pt" aria-label="Umur">
            <div class="me-auto p-2 bd-highlight utama">Hp: </div>
            <div class="p-2 bd-highlight">{{config.menukiri.hp}}</div>
          </div>
          <div class="d-flex bd-highlight mb-3 font-10pt" aria-label="Umur">
            <div class="me-auto p-2 bd-highlight utama">Alamat: </div>
            <div class="p-2 bd-highlight">{{config.menukiri.alamat}}</div>
          </div>
          <div class="d-flex bd-highlight mb-3 font-10pt" aria-label="Umur">
            <div class="me-auto p-2 bd-highlight utama">Status: </div>
            <div class="p-2 bd-highlight text-success" v-if="config.menukiri.status.st===0">
              {{config.menukiri.status.name}}</div>
            <div class="p-2 bd-highlight text-danger" v-else>{{config.menukiri.status.name}}</div>
          </div>
          <hr class="mt-0 mb-3">
          <div class="d-flex justify-content-start">
            <p class="h5 tebaldikit mb-3">Bahasa</p>
          </div>
          <div aria-label="Bahasa" v-for="p in config.menukiri.bahasa" :key="p.name">
            <div class="d-flex bd-highlight font-10pt" aria-label="">
              <div class="me-auto p-2 ps-0 bd-highlight">{{p.name}}</div>
              <div class="p-2 bd-highlight">{{p.value}}%</div>
            </div>
            <hr class="new4 mt-0 mb-0" :style="'width:'+p.value+'%'">
          </div>
          <hr class="mt-3 mb-3">
          <div class="d-flex justify-content-start">
            <p class="h5 tebaldikit mb-3">Hard Skill</p>
          </div>
          <div aria-label="Skill" v-for="p in config.menukiri.skills" :key="p.name">
            <div class="d-flex bd-highlight font-10pt" aria-label="">
              <div class="me-auto p-2 ps-0 bd-highlight">{{p.name}}</div>
              <div class="p-2 bd-highlight">{{p.value}}%</div>
            </div>
            <hr class="new4 mt-0 mb-0" :style="'width:'+p.value+'%'">
          </div>
          <hr class="mt-3 mb-3">
          <div class="d-flex justify-content-start">
            <p class="h5 tebaldikit mb-3">Soft Skill</p>
          </div>
          <div aria-label="Skill" v-for="p in config.menukiri.soft_skills" :key="p.name">
            <div class="d-flex bd-highlight font-10pt" aria-label="">
              <div class="me-auto p-2 ps-0 bd-highlight">{{p.name}}</div>
              <div class="p-2 bd-highlight">{{p.value}}%</div>
            </div>
            <hr class="new4 mt-0 mb-0" :style="'width:'+p.value+'%'">
          </div>
          <hr class="mt-3 mb-3">
          <a :href="config.menukiri.cv">
            <button class="button-kuning">Download CV</button>
          </a>
        </div>
      </div>
      <div class="col-9">
        <Bannerperkenalan :data="config.menukanan.bannerperkenalan"/>
        <Pendidikan :data="config.menukanan.pendidikan" />
        <Pendidikan :data="config.menukanan.pekerjaan" />
        <Portfolio :data="config.menukanan.portfolio" />
      </div>
    </div>
  </div>
</template>
<script>
  import * as config from '../static/data';
  export default {
    data() {
      return {
        config
      }
    }
  }

</script>
