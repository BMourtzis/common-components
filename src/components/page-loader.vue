<template>
  <div>
    <div v-if="status === 0">Loading</div>
    <div v-if="status === 1">
      <slot></slot>
    </div>
    <div v-if="status === 2">Error</div>
  </div>
</template>

<script>
export default {
  props: ["call"],
  data() {
    return {
      status: 0
    };
  },
  created() {
    Promise.resolve(this.call).then(
      () => {
        this.status = 1;
      },
      () => {
        this.status = 2;
      }
    );
  }
};
</script>

<style lang="scss">
</style>


