<template>
  <div>
    <nav class="nav">
      <!-- 所用到的技术 -->
      <div class="techWrap">
        <div
          v-for="(item, index) in techArr"
          :key="index"
          :class="{
            techItem: true,
            visited: techIndex === index ? true : false
          }"
          @click="techIndex = index"
        >
          不限
        </div>
      </div>
      <div class="timeWrap">
        <div
          v-for="(item, index) in times"
          :key="index"
          :class="{
            timeItem: true,
            visited: timeIndex === index ? true : false
          }"
          @click="timeIndex = index"
        >
          {{ item.time }}
        </div>
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
      techIndex: 0,
      times: [
        {
          time: '2020-2024'
        },
        {
          time: '2025-2029'
        }
      ],
      techArr: ['不限', 'Vue']
    };
  }
};
</script>
<style lang="scss">
.nav {
  padding: 27px;
  background-color: white;
  border-radius: 10px;
  color: #4d555d;
  .techWrap {
    display: flex;
    .techItem {
      margin-right: 20px;
      padding: 5px 10px;
      cursor: pointer;
      &:hover {
        background-color: #f6f9ff;
      }
    }
    .visited {
      background-color: #f6f9ff;
    }
  }
  .timeWrap {
    display: flex;
  }
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
