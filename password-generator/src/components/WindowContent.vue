<template>
  <div class="window">
    <h1 class="window-title">title placeholder</h1>
    <div v-for="item in items" :key="item.id">
      <WindowSection
        :text="item.text"
        :inputPlaceholder="item.inputPlaceholder"
        :value="item.value"
        v-if="item.id !== 5"
      />
      <WindowSection
        v-else
        :text="item.text"
        :inputPlaceholder="item.inputPlaceholder"
        :value="item.value"
        @mouseover="showAlert"
      />
    </div>
  </div>
</template>

<script>
import WindowSection from './WindowComponents/WindowSection.vue';

export default {
  name: 'WindowContent',
  components: {
    WindowSection,
  },
  data() {
    return {
      items: [
        { id: 1, text: 'Length', inputPlaceholder: 'Length' },
        { id: 2, text: 'Ammount of numbers', inputPlaceholder: 'Ammount of numbers' },
        { id: 3, text: 'Ammount of special characters', inputPlaceholder: 'Ammount of special characters' },
        { id: 4, text: 'Required phrase', inputPlaceholder: 'Required phrase' },
        { id: 5, text: 'Generate', inputPlaceholder: 'Output' }
      ]
    };
  },
  methods: {
    showAlert() {
      const length = this.items.find(item => item.id === 1).value;
      alert(`${length}`);
    }
  }
};
</script>

<style scoped lang="scss">

</style>
