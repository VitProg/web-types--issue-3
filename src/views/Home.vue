<template>
  <div class="home">
    <!-- IDE does not see the component described in web-types.json and autocomplete do not work =(( -->
    <cmp-test></cmp-test>
    <!-- IDE does not see the component described in web-types.json and autocomplete do not work =(( -->
    <CmpTest></CmpTest>

    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src
import '@/components/CTest.vue';

@Component({
  components: {
    HelloWorld,
  },
})
export default class Home extends Vue {}
</script>
