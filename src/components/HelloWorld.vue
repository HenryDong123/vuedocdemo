<template>
  <div :class="this.$style.hello">
    <h1>computed demo</h1>
    {{ fullName }}
    <button @click="changeX">改姓</button>
    <div v-for="(item, index) in listData" :key="index">
      <div v-show="item.show">{{ item.Date }}</div>
      <div @click="change(index)">{{ item.time }}</div>
      <div>{{ item.subject }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      i: -1,
      firstName: "Henry",
      lastName: "Dong",
      listData: [
        {
          code: "1",
          Date: "1月5日",
          time: "10:30-11:20",
          subject: "语文",
          countDown: "2",
          show: ""
        },
        {
          code: "2",
          Date: "1月6日",
          time: "10:30-11:20",
          subject: "数学",
          countDown: "2",
          show: ""
        },
        {
          code: "3",
          Date: "1月7日",
          time: "10:30-11:20",
          subject: "吃饭",
          countDown: "2",
          show: "true"
        },
        {
          code: "4",
          Date: "1月8日",
          time: "10:30-11:20",
          subject: "骑马",
          countDown: "2",
          show: "true"
        },
        {
          code: "5",
          Date: "1月9日",
          time: "10:30-11:20",
          subject: "射箭",
          countDown: "2",
          show: ""
        },
        {
          code: "6",
          Date: "1月10日",
          time: "10:30-11:20",
          subject: "开炮",
          countDown: "2",
          show: "true"
        },
        {
          code: "7",
          Date: "1月11日",
          time: "10:30-11:20",
          subject: "睡觉",
          countDown: "1",
          show: "true"
        }
      ]
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
    },
    change(index) {
      this.listData[index].show = !this.listData[index].show;
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
