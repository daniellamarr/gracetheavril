<template>
  <div class="pagination">
    <div class="line" />
    <div class="pagination-item">
      <div class="currentPage" v-bind:style="{color: mode === 'dark' ? darkMode.color : lightMode.color}">{{currentPage}}/</div>
      <div class="totalPage" v-bind:style="{color: mode === 'dark' ? darkMode.totalPageColor : lightMode.totalPageColor}">05</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Pagination',
  props: {
    mode: String,
    currentPage: String
  },
  data() {
    return {
      darkMode: {
        color: '#E0FFF0',
        totalPageColor: '#fff',
      },
      lightMode: {
        color: '#00CC69',
        totalPageColor: '#bdbdbd'
      }
    }
  },
}
</script>

<style lang="scss" scoped>
  @import '../scss/variables';

  .pagination {
    position: fixed;
    right: 3%;
    top: 250px;
    transform: rotate(-90deg);
    display: flex;

    .line {
      width: 100px;
      height: 0;
      border: 1px solid $white;
      margin-top: 40px;
      margin-right: 40px;
    }

    .pagination-item {
      display: flex;
      align-items: center;

      .currentPage {
        font-size: 64px;
        color: $light-teal;
      }

      .totalPage {
        font-size: 32px;
        color: $white;
      }
    }
  }
</style>