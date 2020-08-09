<template>
  <div>
    <nav class="nav">
      <div
        v-for="(item, index) in times"
        :key="index"
        :class="{ timeItem: true, visited: timeIndex === index ? true : false }"
        @click="timeIndex = index"
      >
        {{ item.time }}
      </div>
    </nav>
    <main></main>
  </div>
</template>
<script>
export default {
  data() {
    return {
      timeIndex: true,
      times: [
        {
          time: '2019-2020'
        },
        {
          time: '2021-2020'
        }
      ]
    };
  }
};
</script>
<style lang="scss">
.nav {
  display: flex;
  padding: 27px;
  background-color: white;
  border-radius: 10px;
  .timeItem {
    width: 100px;
    line-height: 30px;
    margin-right: 20px;
    text-align: center;
    cursor: pointer;
    &:hover {
      background-color: #f6f9ff;
    }
  }
  .visited {
    background-color: #f6f9ff;
  }
}
</style>
