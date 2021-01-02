<template>
  <div class="socials">
    <a href="https://twitter.com/gracetheAvril" target="_blank" v-bind:style="{color: mode === 'dark' ? darkMode.color : lightMode.color}">
      <div v-bind:style="{borderColor: mode === 'dark' ? darkMode.color : lightMode.color}">
        <ThemifyIcon icon="twitter-alt" />
      </div>
    </a>
    <a href="https://www.instagram.com/_theavril/" target="_blank" v-bind:style="{color: mode === 'dark' ? darkMode.color : lightMode.color}">
      <div v-bind:style="{borderColor: mode === 'dark' ? darkMode.color : lightMode.color}">
        <ThemifyIcon icon="instagram" />
      </div>
    </a>
    <a href="" v-bind:style="{color: mode === 'dark' ? darkMode.color : lightMode.color}">
      <div v-bind:style="{borderColor: mode === 'dark' ? darkMode.color : lightMode.color}">
        <ThemifyIcon icon="linkedin" />
      </div>
    </a>
  </div>
</template>

<script>
import ThemifyIcon from 'vue-themify-icons';

export default {
  name: 'Socials',
  components: {
    ThemifyIcon
  },
  props: {
    mode: String
  },
  data() {
    return {
      darkMode: {
        color: '#fff',
      },
      lightMode: {
        color: '#4f4f4f'
      }
    }
  },
}
</script>

<style lang="scss" scoped>
  @import '../scss/variables';

  .socials {
    position: fixed;
    right: 10.5%;
    bottom: 200px;

    a {
      color: $white;
      text-decoration: none;
    }

    div {
      padding: 8px;
      border: 1px solid #fff;
      border-radius: 30px;
      margin-bottom: 15px;
      display: flex;
      align-items: center;
    }
  }
</style>