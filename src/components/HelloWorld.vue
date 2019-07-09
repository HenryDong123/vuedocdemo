<template>
  <div :class="this.$style.hello">
    <h1>computed demo</h1>
    {{ fullName }}
    <button @click="changeX">改姓</button>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      firstName: "Henry",
      lastName: "Dong"
    };
  },
  computed: {
    fullName() {
      return this.firstName + "" + this.lastName;
    }
  },
  methods: {
    changeX() {
      this.firstName = "Tom";
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss" module>
.hello {
  border-bottom: 1px slategray solid;
}
</style>
