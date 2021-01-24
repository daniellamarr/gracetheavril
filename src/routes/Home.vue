<template>
  <Header v-bind:mode="mode" v-bind:changeMode="changeMode" />
  <section id="body" v-bind:style="{backgroundColor: mode === 'dark' ? darkMode.bgColor : lightMode.bgColor}">
    <div class="scrollDown">
      <div class="line" v-bind:style="{borderColor: mode === 'dark' ? darkMode.color : lightMode.color}" />
      <p v-bind:style="{color: mode === 'dark' ? darkMode.color : lightMode.color}">Scroll Down</p>
    </div>
    <Pagination v-bind:mode="mode" v-bind:currentPage="currentPage" />
    <Socials v-bind:mode="mode" />
    <section id="home">
      <div id="welcome">
        <h4 v-bind:style="{color: mode === 'dark' ? darkMode.color : lightMode.color}">Hello,</h4>
        <h1 v-bind:style="{color: mode === 'dark' ? darkMode.color : lightMode.color}">I am <br /> Grace<span>.</span></h1>
        <div class="hireMe">
          <button v-bind:style="{color: mode === 'dark' ? darkMode.color : '#00CC69'}">Hire Me <span><ThemifyIcon icon="angle-right" /></span></button>
        </div>
      </div>
      <div class="circle-ring">
        <img src="../assets/circle-ring.svg" alt="">
      </div>
    </section>
    <section id="about" v-bind:style="{backgroundColor: mode === 'dark' ? darkMode.bgColor : lightMode.bgColor}">
      <div class="about-section">
        <div class="about-circle-ring">
          <img src="../assets/circle-ring.svg" alt="">
        </div>
        <div class="about-details">
          <h1 v-bind:style="{color: mode === 'dark' ? darkMode.color : lightMode.color}">Need help with writing?</h1>
          <p v-bind:style="{color: mode === 'dark' ? darkMode.color : lightMode.color}">
            A young writer doing young writer things…and a little bit more!
            Writer. Beautiful mind enthusiast.
            Lorem ipsum dolor sit amet, consectetur adipiscing elit.
            Pellentesque porta sapien varius eleifend porta turpis nec lacus nunc.
            Pharetra dignissim amet imperdiet nunc, nibh euismod odio purus.
            Ultrices ut sapien malesuada turpis. Tempus commodo egestas gravida ultricies et.<br />

            A young writer doing young writer things…and a little bit more!
            Writer. Beautiful mind enthusiast.
            Lorem ipsum dolor sit amet, consectetur adipiscing elit.
            Pellentesque porta sapien varius eleifend porta turpis nec lacus nunc.
            Pharetra dignissim amet imperdiet nunc, nibh euismod odio purus.
            Ultrices ut sapien malesuada turpis. Tempus commodo egestas gravida ultricies et.
          </p>
        </div>
        <div class="about-image">
          <div class="image-box" v-bind:style="{backgroundColor: mode === 'dark' ? darkMode.imageBox : lightMode.imageBox}">
            <img src="../assets/grace.png" alt="">
          </div>
        </div>
      </div>
    </section>
    <section id="contact"
      v-bind:style="{
        backgroundColor: mode === 'dark' ? darkMode.bgColor : lightMode.bgColor,
        color: mode === 'dark' ? darkMode.color : lightMode.color
      }">
      <div class="contact-section">
        <div class="getintouch">
          <h1>Get in touch!</h1>
          <p>Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumyeirmod </p>
        </div>
        <div class="form-section">
          <div class="contact-info">
            <div>
              <span><ThemifyIcon icon="email" /></span>Email Address
              <p>adeolaakandeg@gmail.com</p>
            </div>
            <div>
              <span><ThemifyIcon icon="headphone-alt" /></span>Phone Number
              <p>+234 81 567 285 097</p>
            </div>
          </div>
          <div class="contact-form">
            <div class="input-flex">
              <div class="input">
                <input type="text" placeholder="Name" :style="{color: mode === 'dark' ? darkMode.color : lightMode.color, borderColor: mode === 'dark' ? darkMode.color : lightMode.color}">
              </div>
              <div class="input">
                <input type="text" placeholder="Email" :style="{color: mode === 'dark' ? darkMode.color : lightMode.color, borderColor: mode === 'dark' ? darkMode.color : lightMode.color}">
              </div>
            </div>
            <div>
              <input type="text" placeholder="Message" :style="{color: mode === 'dark' ? darkMode.color : lightMode.color, borderColor: mode === 'dark' ? darkMode.color : lightMode.color}">
            </div>
            <div class="form-button">
              <button>
                Submit <span><ThemifyIcon icon="angle-right" /></span>
              </button>
            </div>
          </div>
        </div>
      </div>
    </section>
  </section>
</template>

<script>
import ThemifyIcon from 'vue-themify-icons';
import Header from '../components/Header';
import Socials from '../components/Socials';
import Pagination from '../components/Pagination';

export default {
  name: 'Home',
  components: {
    ThemifyIcon,
    Header,
    Socials,
    Pagination
  },
  data() {
    return {
      mode: 'dark',
      currentPage: '01',
      darkMode: {
        bgColor: '#02120D',
        color: '#fff',
        imageBox: '#032016'
      },
      lightMode: {
        bgColor: '#fff',
        color: '#02120D',
        imageBox: '#f2f2f2'
      }
    }
  },
  methods: {
    changeMode() {
      this.mode === 'dark' ? this.mode = 'light' : this.mode = 'dark';
    }
  }
}
</script>

<style lang="scss" scoped>
  @import '../scss/variables';
  #body {
    background-color: $black;
    height: 100vh;
    width: 100%;
  }

  #home {
    height: 100vh;
    background-attachment: fixed;
  }

  #welcome {
    position: absolute;
    left: 25%;
    top: 150px;
    z-index: 1;

    h1, h4 {
      color: $white;
    }

    h1 {
      font-size: 160px;
      line-height: 170px;
      margin-left: -8px;
      margin-top: 20px;

      span {
        color: $teal;
      }
    }

    h4 {
      font-size: 32px;
    }

    button {
      background-color: transparent;
      padding: 15px;
      padding-left: 25px;
      padding-right: 25px;
      color: $white;
      letter-spacing: 1px;
      border: 1px solid $teal;
      border-radius: 40px;
      outline: 0;
      cursor: pointer;
      margin-top: 20px;
      text-transform: uppercase;
      font-weight: bold;

      span {
        margin-left: 80px;
      }
    }
  }

  #about {
    background-color: $black;
    height: 100vh;
    padding-left: 200px;
    padding-right: 200px;
    color: $white;

    .about-section {
      padding-top: 150px;
      display: flex;

      .about-details {
        width: 50%;
        h1 {
          font-size: 32px;
        }

        p {
          line-height: 30px;
        }
      }

      .about-image {
        padding-left: 50px;
        padding-top: 100px;
        position: relative;

        .image-box {
          height: 350px;
          width: 350px;
          background-color: $black2;
          border-radius: 30px;
          display: flex;
          align-items: center;
          justify-content: center;

          img {
            width: 80%;
            margin-bottom: -70px;
          }
        }
      }
    }

    .about-circle-ring {
      position: absolute;
      width: 300px;
      height: 300px;
      right: 200px;
      opacity: 0.3;

      img {
        width: 100%;
      }
    }
  }

  #contact {
    background-color: $black;
    height: 100vh;
    padding-left: 200px;
    padding-right: 200px;
    color: $white;

    .contact-section {
      padding-top: 150px;

      .getintouch {
        width: 50%;

        h1 {
          font-size: 32px;
        }
      }

      .form-section {
        margin-top: 200px;
        display: flex;

        .contact-info {
          & > div {
            span {
              margin-right: 10px;
            }
            p {
              font-size: 24px;
              margin-top: 20px;
            }
          }

          & > div:first-child {
            margin-bottom: 50px;
          }
        }

        .contact-form {
          margin-left: 70px;
          width: 50%;

          .input-flex {
            display: flex;
            width: 100%;
            margin-bottom: 50px;

            .input {
              width: 50%;
            }

            .input:first-child {
              margin-right: 30px;
            }
          }

          input {
            background-color: transparent;
            width: 100%;
            color: $white;
            border: none;
            border-bottom: 1px solid $white;
            padding: 8px;
          }

          .form-button {
            margin-top: 50px;

            button {
              background-color: $teal;
              padding: 15px;
              padding-left: 25px;
              padding-right: 25px;
              color: $white;
              letter-spacing: 1px;
              border: 1px solid $teal;
              border-radius: 40px;
              outline: 0;
              cursor: pointer;
              margin-top: 20px;
              text-transform: uppercase;
              font-weight: bold;

              span {
                margin-left: 80px;
              }
            }
          }
        }
      }
    }
  }

  .circle-ring {
    position: absolute;
    top: 100px;
    right: 300px;
    opacity: 0.3;
  }

  .scrollDown {
    position: fixed;
    bottom: 250px;
    left: 4%;
    transform: rotate(-90deg);
    display: flex;

    p {
      color: $white;
      text-transform: uppercase;
    }

    .line {
      width: 50px;
      height: 0;
      border: 1px solid $white;
      margin-top: 8px;
      margin-right: 20px;
    }
  }
</style>