<template>
  <button
    @click="click"
    class="bg-transparent hover:bg-red-500 text-red-700 font-semibold hover:text-white py-2 px-2 border border-red-500 hover:border-transparent rounded"
  >
    <beat-loader
      v-show="isloading"
      :loading="isLoading"
      :color="'#EF4444'"
      :size="8"
    ></beat-loader>
    <div v-show="!isLoading">
      <p><slot></slot></p>
    </div>
  </button>
</template>

<script>
export default {
  name: 'PxButton',
  props: {
    isLoading: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    click() {
      this.$emit('click');
    },
  },
};
</script>
