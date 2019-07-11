<template>
  <div :class="this.$style.ref">
    <div @click="handClick">{{ number }}</div>
  </div>
</template>

<script>
export default {
  name: "ref",
  data() {
    return {
      number: 0,
      a: true
    };
  },
  methods: {
    handClick() {
      this.number++;
      this.$emit("change");
    }
  }
};
</script>

<style lang="scss" module>
.ref {
  border-bottom: 1px slategray solid;
}
</style>
