<template>
  <v-app>
    <v-main>
      <Traine/>
    </v-main>
  </v-app>
</template>

<script>
import Traine from './components/Traine.vue';

export default {
  name: 'App',

  components: {
    Traine
},

  data: () => ({
    //
  }),
};
</script>
