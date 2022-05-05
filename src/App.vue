<template>
  <div class="container">
    <ul class="nav nav-pills">
      <li class="nav-item">
        <a class="nav-link" @click="activeTab = 'main'" :class ="{active: activeTab === 'main'}" aria-current="page" href="#">Главная</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" @click="activeTab = 'catalog'" :class="{active: activeTab === 'catalog' }" href="#">Каталог</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" @click="activeTab = 'bascet'" :class="{active: activeTab === 'bascet' }" href="#">Корзина</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" @click="activeTab = 'profile'" :class="{active: activeTab === 'profile' }" href="#" >Профиль</a>
      </li>
    </ul>
    <myManu  v-if="activeTab === 'main' " @create="createPost"/>
    <catalog v-if="activeTab === 'catalog'"/>
    <profile v-if="activeTab === 'profile' "/>
    <bascet  v-if="activeTab === 'bascet'" :bascetList="bascetList" />

  </div>

</template>

<script>
import myManu  from '@/components/myManu.vue';
import catalog from '@/components/myCatalog.vue';
import profile from '@/components/myProfile.vue';
import bascet  from '@/components/myBascet.vue';

export default {
  name: 'App',
  components: {
    myManu,
    catalog,
    profile,
    bascet,

  },
  data() {
    return {
      activeTab: 'main',
      bascetList: [

      ],
    }
  },

  methods: {
    createPost(post) {
      this.bascetList.push(post);
    },
  }
}
</script>

<style>
.container {
  padding-top: 10px;
  width: 500px;
  margin: auto;
}
</style>