<template>
  <div class="p-3">
    <div class="mx-auto max-w-screen-lg flex items-center justify-center">
      <router-link to="/" class="mx-2 btn">Home</router-link>
      <router-link to="/all" class="mx-2 btn">All Quotes</router-link>
    </div>
  </div>
  <router-view />
</template>

<script>
import { useStore } from 'vuex';
import { onMounted } from 'vue';

export default {
  setup () {
    const store = useStore();

    onMounted(() => {
      store.commit('GetAllQuotes');
    });
  }
}
</script>