<template>
  <div :class="this.$style.watch">
    <h1>watch demo</h1>
    <p>
      Ask a yes/no question:
      <input v-model="question" />
    </p>
    <p>{{ answer }}</p>
  </div>
</template>

<script>
export default {
  name: "watch",
  data() {
    return {
      question: "",
      answer: "问个问题老铁"
    };
  },
  watch: {
    question(newQuestion, oldQuestion) {
      this.answer = "我等你停下来";
      this.debouncedGetAnswer();
    }
  },
  created() {
    this.debouncedGetAnswer = _.debounced(this.getAnswer, 500);
  },
  methods: {
    getAnswer() {
      if (this.question.indexOf("?") === -1) {
        this.answer = "问完了赶紧打个问号知道不";
        return;
      }
      this.answer = "先想想";
      axios.get("https://yesno.wtf/api").then(
        (res => {
          this.answer = _.capitalize(res.data.answer);
        },
        err => {
          this.answer = "错了错了" + err;
        })
      );
    }
  }
};
</script>

<style lang="scss" module>
.watch {
  border-bottom: 1px slategray solid;
}
</style>
