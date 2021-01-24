<template>
  <header>
    <ul v-bind:style="{color: mode === 'dark' ? darkMode.color : lightMode.color}">
      <li class="mode" @click="changeMode">
        {{ mode === 'dark' ? 'Light' : 'Dark' }}
      </li>
      <li>
        <img src="../assets/logo-light.png" v-bind:style="{width: '70px'}" alt="" v-if="mode==='dark'">
        <img src="../assets/logo.png" v-bind:style="{width: '70px'}" alt="" v-else>
      </li>
      <li class="menu-item">
        <div>
          Menu
        </div>
        <div>
          <div class="menu" />
          <div class="menu" />
        </div>
      </li>
    </ul>
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: {
    mode: String,
    changeMode: Function
  },
  data() {
    return {
      darkMode: {
        bgColor: '#02120D',
        color: '#fff',
      },
      lightMode: {
        bgColor: '#fff',
        color: '#02120D'
      }
    }
  },
}
</script>

<style lang="scss">
  @import '../scss/variables';
  header {
    position: fixed;
    width: 100%;
    padding-top: 50px;

    ul {
      list-style: none;
      display: flex;
      justify-content: center;
      color: $white;

      li {
        text-transform: uppercase;
        margin-right: 33.3%;

        &:first-child {
          margin-left: 33.3%;
        }

        &.mode {
          cursor: pointer;
        }

        &.menu-item {
          display: flex;
          align-items: center;

          & > div:first-child {
            margin-right: 10px;
            margin-top: -5px;
          }
        }

        &.menu-item:hover {
          .menu:first-child {
            transform: rotate(45deg);
          }
          .menu:last-child {
            transform: rotate(-45deg);
          }
        }

        div.menu {
          width: 28px; 
          height: 1px; 
          margin: 0 0 5px 0; 
          background: $white; 
          transition: all 0.5s ease-out;
        }
      }
    }
  }
</style>