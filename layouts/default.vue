<template>
  <div class="fullpage-container">
    <div class="fullpage-wp" v-fullpage="opts" ref="fullpage">  

      <div class="page-1 page">
        <!-- Header built here because it wasnt working as a component (TODO: Fix later) -->
        <div class="img-container">

        <header>
          <div class="header-logo">
              <a href="/"><img src="https://imgur.com/4QMsf3W.png" alt="img-logo"></a>
          </div>
          <nav>
            <ul>

              <li><a :class="{active:index ==0}" @click="moveTo(1)">info</a></li>

              <li><a :class="{active:index ==1}" @click="moveTo(2)">collection</a></li>

              <li><a :class="{active:index ==2}" @click="moveTo(3)">bio</a></li>

            </ul>
          </nav>
        </header>

        </div>
      </div>

      <div class="page-2 page">
        <nuxt/>
      </div>

      <div class="page-3 page">
        <Gallery/>
      </div>

      <div class="page-4 page">
        <Bio/>
      </div>

    </div>
  </div>
</template>

<script>
import 'animate.css'
import 'fullpage-vue/src/fullpage.css'
import Gallery from '~/components/Gallery.vue'
import Bio from '~/components/Bio.vue'

export default {
      data() {
    return {
      index: 0,
      opts: {
        start: 0,
        dir: 'v',
        duration: 500,
        beforeChange: function(ele, current, next) {
            console.log('before', current, next)
            this.index = next;
        },
        afterChange: function(ele, current) {
            this.index = current;
            console.log('after', current)
        }
      }
    }
  },
    methods: {
        moveTo: function(index) {
            this.$refs.fullpage.$fullpage.moveTo(index, true);
        }
  },
    components: {
        Gallery,
        Bio
    }
}
</script>


<style>
@import url('https://fonts.googleapis.com/css?family=Work+Sans:300');

html {
  font-family: "Work Sans", Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*, *:before, *:after {
  box-sizing: border-box;
  margin: 0;
}

/* HEADER CSS */

.img-container {
    min-height: 100vh;
    background-image: url('https://imgur.com/Rhzskdq.jpg');
    background-size: 100vw;
    background-repeat: no-repeat;
    z-index: 1;
}

header {
    display: flex;
    flex: 1;
    flex-direction: row;
    width: 100%;
    height: 100px;
    align-items: center;
    justify-content: space-between;
    background-color: rgba(0, 0, 0, 0);
    position: absolute;
    z-index: 2;
}

.header-logo {
    display: flex;
    justify-content: flex-start;
    padding-left: 30px;
}

nav {
    display: flex;
    flex-direction: row;
    height: 80px;
    width: 40%;
    align-items: center;
    justify-content: flex-end;
}

ul {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    align-items: center;
}

li {
    margin: 2px 80px 2px 80px;
}

header a {
    font-size: 20px;
    font-family: 'Work Sans';
    font-weight: 300;
    letter-spacing: 3px;
    color: #fff;
    text-decoration: none;
    cursor: pointer;
}

 /* BODY CSS */

.fullpage-container {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
}

.page {
  width: 100vw;
  height: 100vh !important;
}

</style>
