<template>
  <div class="home">
    <HelloWorld />
    <Watch />
    <Ref ref="one" @change="handleChange" />
    <div>{{ total }}</div>
    <Ref ref="two" @change="handleChange" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import Watch from "@/components/watch.vue";
import Ref from "@/components/ref";

export default {
  name: "home",
  components: {
    HelloWorld,
    Watch,
    Ref
  },
  data() {
    return {
      total: 0
    };
  },
  methods: {
    handleChange() {
      this.total = this.$refs.one.number + this.$refs.two.number;
    }
  }
};
</script>
