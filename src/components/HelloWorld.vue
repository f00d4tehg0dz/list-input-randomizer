<template>
  <div class="hello">
    <!-- <h1>{{ msg }}</h1> -->
    <h2>Music Theory Generator </h2>
    <div id="main">
      <div class="inner">
        <header>
          <div class="mode-toggle" @click="modeToggle" :class="darkDark">
            <div class="toggle">
              <div id="dark-mode" type="checkbox"></div>
            </div>
          </div>
          <p></p>
        </header>
        <section class="tiles">
          <article class="style1">
            <span class="image">
              <!-- <img src="images/.jpg" alt=""> -->
              <p>{{ chosenKeyArr }}</p>
              <button style="backgroundColor:rgb(0 149 255)" v-on:click="randomizeKey">Key</button>
              <button type="button" class="greenBtn" @click="addKeyArr">
                +
              </button>
            </span>
              <form action="post">
                <div v-for="(key, index) in keyArr" :key="index">
                  <div class="flex justify-start ml-2 mt-4 inputArr">
                    <input type="text" name="keyArr"
                      v-model="keyArr[index]" v-on:input="changed"
                      placeholder="enter you keys" />
                    <button type="button"
                      class="ml-2 rounded-md border px-3 py-2 bg-red-600 text-white"
                      @click="removeKeyArr(index)" v-show="index != 0">
                      -
                    </button>
                  </div>
                </div>
              </form>
              <!-- {{ keyArr | json }} -->
              <!-- <select id="s1">
                <option value="" v-for="key in keyArr" v-bind:key="key">
                  {{ key }}
                </option>
              </select> -->
            <h2></h2>
            <div class="content">
              <p></p>
            </div>
          </article>
          <article class="style2">
            <span class="image">
              <!-- <img src="images/.jpg" alt=""> -->
              <p>{{ chosenScaleArr }}</p>
              <button style="backgroundColor:#FF661A" v-on:click="randomizeScale">Scale</button>
              <button type="button" class="greenBtn" @click="addScaleArr">
                +
              </button>
            </span>
              <form action="post">
                <div v-for="(scale, index) in scaleArr" :key="index">
                  <div class="flex justify-start ml-2 mt-4 inputArr">
                    <input type="text" name="scaleArr"
                      v-model="scaleArr[index]" v-on:input="changed"
                      placeholder="enter you scales" />
                    <button type="button"
                      class="ml-2 rounded-md border px-3 py-2 bg-red-600 text-white"
                      @click="removeScaleArr(index)" v-show="index != 0">
                      -
                    </button>
                  </div>
                </div>
              </form>
              <!-- <select id="s2">
                <option value="" v-for="scale in scaleArr" v-bind:key="scale">
                  {{ scale }}
                </option>
              </select> -->
            <h2></h2>
            <div class="content">
              <p></p>
            </div>
          </article>
          <article class="style3">
            <span class="image">
              <!-- <img src="images/.jpg" alt=""> -->
              <p>{{ chosenTempoArr }}</p>
              <button style="backgroundColor:#12b9ad" v-on:click="randomizeTempo">Tempo</button>
              <button type="button" class="greenBtn" @click="addTempoArr">
                +
              </button>
            </span>
              <form action="post">
                <div v-for="(tempo, index) in tempoArr" :key="index">
                  <div class="flex justify-start ml-2 mt-4 inputArr">
                    <input type="text" name="tempoArr"
                      v-model="tempoArr[index]" v-on:input="changed"
                      placeholder="enter you tempo" />
                    <button type="button"
                      class="ml-2 rounded-md border px-3 py-2 bg-red-600 text-white"
                      @click="removeTempoArr(index)" v-show="index != 0">
                      -
                    </button>
                  </div>
                </div>
              </form>
              <!-- <select id="s3">
                <option value="" v-for="tempo in tempoArr" v-bind:key="tempo">
                  {{ tempo }}
                </option>
              </select> -->
            <h2></h2>
            <div class="content">
              <p></p>
            </div>
          </article>
          <article class="style4">
            <span class="image">
              <!-- <img src="images/.jpg" alt=""> -->
              <p>{{ chosenTArr }}</p>
              <button style="backgroundColor:#7942ff" v-on:click="randomizeT">Technique</button>
              <button type="button" class="greenBtn" @click="addTArr">
                +
              </button>
            </span>
              <form action="post">
                <div v-for="(technique, index) in tArr" :key="index">
                  <div class="flex justify-start ml-2 mt-4 inputArr">
                    <input type="text" name="techniqueArr"
                      v-model="tArr[index]" v-on:input="changed"
                      placeholder="enter you technique" />
                    <button type="button"
                      class="ml-2 rounded-md border px-3 py-2 bg-red-600 text-white"
                      @click="removeTArr(index)" v-show="index != 0">
                      -
                    </button>
                  </div>
                </div>
              </form>
              <!-- <select id="s4">
                <option value="" v-for="technique in tArr" v-bind:key="technique">
                  {{ technique }}
                </option>
              </select> -->
            <h2></h2>
            <div class="content">
              <p></p>
            </div>
          </article>
          <article class="style5">
            <span class="image">
              <!-- <img src="images/.jpg" alt=""> -->
              <p>{{ chosenFxArr }}</p>
              <button style="backgroundColor:#33b65b" v-on:click="randomizeFx">Fx</button>
              <button type="button" class="greenBtn" @click="addFxArr">
                +
              </button>
            </span>
              <form action="post">
                <div v-for="(fx, index) in fxArr" :key="index">
                  <div class="flex justify-start ml-2 mt-4 inputArr">
                    <input type="text" name="fxArr"
                      v-model="fxArr[index]" v-on:input="changed"
                      placeholder="enter you fx" />
                    <button type="button"
                      class="ml-2 rounded-md border px-3 py-2 bg-red-600 text-white"
                      @click="removeFxArr(index)" v-show="index != 0">
                      -
                    </button>
                  </div>
                </div>
              </form>
              <!-- <select id="s5">
                <option value="" v-for="fx in fxArr" v-bind:key="fx">
                  {{ fx }}
                </option>
              </select> -->
            <h2></h2>
            <div class="content">
              <p></p>
            </div>
          </article>
          <article class="style6">
            <span class="image">
              <!-- <img src="images/.jpg" alt=""> -->
              <p>Randomize All</p>
              <button v-on:click="randomizeAll">Randomize</button>
            </span>
            <h2></h2>
            <div class="content">
              <p></p>
            </div>
          </article>
        </section>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      darkMode: false,
      // Default Arrays
      keyArr: [
        'A',
        'B',
        'C',
        'D',
        'E',
        'F',
        'G',
        '#',
        'b',
      ],
      chosenKeyArr: 'Key',
      scaleArr: [
        'Ionian',
        'Aeolian',
        'Mixolydian',
        'Ownedian',
      ],
      chosenScaleArr: 'Scale',
      tempoArr: [
        '70',
        '80',
        '90',
        '100',
        '120',
        '140',
      ],
      chosenTempoArr: 'Tempo',
      tArr: [
        'Harmonics',
        'Chords',
        'Octaves',
        'Pale Muting',
        'Chromatic',
        'Tapping',
        'Whammy Bar',
        'Pinch Harmonics',
        'Sweeping',
        'Finger Picking',
        'Rests',
        'Odd Time/Rhythm',
      ],
      chosenTArr: 'Technique',
      fxArr: [
        'Wah',
        'Delay',
        'Filter',
        'Robot',
        'Octaver',
        'Heavy Reverb',
        'Dry',
        'Beat Repeat',
        'Pitch Control',
      ],
      chosenFxArr: 'Fx',
    };
  },
  methods: {
    addKeyArr() {
      this.keyArr.push('');
    },
    removeKeyArr(index) {
      this.keyArr.splice(index, 1);
    },
    addScaleArr() {
      this.scaleArr.push('');
    },
    removeScaleArr(index) {
      this.scaleArr.splice(index, 1);
    },
    addTempoArr() {
      this.tempoArr.push('');
    },
    removeTempoArr(index) {
      this.tempoArr.splice(index, 1);
    },
    addTArr() {
      this.tArr.push('');
    },
    removeTArr(index) {
      this.tArr.splice(index, 1);
    },
    addFxArr() {
      this.fxArr.push('');
    },
    removeFxArr(index) {
      this.fxArr.splice(index, 1);
    },
    // Dark Mode
    dark() {
      document.querySelector('body').classList.add('dark-mode');
      this.darkMode = true;
      this.$emit('dark');
    },
    // Light Mode
    light() {
      document.querySelector('body').classList.remove('dark-mode');
      this.darkMode = false;
      this.$emit('light');
    },
    // Mode Toggle
    modeToggle() {
      if (this.darkMode || document.querySelector('body').classList.contains('dark-mode')) {
        this.light();
      } else {
        this.dark();
      }
    },
    // Shuffle Functions
    shuffleKeyArray() {
      const chosenNumber = Math.floor(Math.random() * this.keyArr.length);
      this.chosenKeyArr = this.keyArr[chosenNumber];
    },
    shuffleScaleArray() {
      const chosenNumber = Math.floor(Math.random() * this.scaleArr.length);
      this.chosenScaleArr = this.scaleArr[chosenNumber];
    },
    shuffleTempoArray() {
      const chosenNumber = Math.floor(Math.random() * this.tempoArr.length);
      this.chosenTempoArr = this.tempoArr[chosenNumber];
    },
    shuffleTArray() {
      const chosenNumber = Math.floor(Math.random() * this.tArr.length);
      this.chosenTArr = this.tArr[chosenNumber];
    },
    shuffleFxArray() {
      const chosenNumber = Math.floor(Math.random() * this.fxArr.length);
      this.chosenFxArr = this.fxArr[chosenNumber];
    },
    // Randomize Func
    randomizeKey() {
      this.shuffleKeyArray(this.keyArr);
    },
    randomizeScale() {
      this.shuffleScaleArray(this.scaleArr);
    },
    randomizeTempo() {
      this.shuffleTempoArray(this.tempoArr);
    },
    randomizeT() {
      this.shuffleTArray(this.tArr);
    },
    randomizeFx() {
      this.shuffleFxArray(this.fxArr);
    },
    randomizeAll() {
      this.shuffleKeyArray(this.keyArr);
      this.shuffleScaleArray(this.scaleArr);
      this.shuffleTempoArray(this.tempoArr);
      this.shuffleTArray(this.tArr);
      this.shuffleFxArray(this.fxArr);
    },
    changed() {
      // console.log(this.keyArr);
      // console.log(this.scaleArr);
      // console.log(this.tempoArr);
      // console.log(this.tArr);
      // console.log(this.fxArr);
    },
  },
  computed: {
    darkDark() {
      return this.darkMode && 'darkmode-toggled';
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
input[type=text],
select {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 10px;
  box-sizing: border-box;
}

.inputArr {
  display: flex;
  flex-wrap: nowrap;
  flex-direction: row;
  align-items: center;
}
form {
  display: flex;
  flex-direction: column;
  align-content: space-around;
  flex-wrap: wrap;
  justify-content: flex-start;
}
.mode-toggle {
  position: relative;
  padding: 0;
  width: 44px;
  height: 24px;
  min-width: 36px;
  min-height: 20px;
  background-color: #262626;
  border: 0;
  border-radius: 24px;
  outline: 0;
  overflow: hidden;
  cursor: pointer;
  z-index: 2;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
  -webkit-touch-callout: none;
  appearance: none;
  transition: background-color 0.5s ease;
  margin: 0 auto;
}

.mode-toggle .toggle {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  margin: auto;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  border: 3px solid transparent;
  box-shadow: inset 0 0 0 2px #a5abba;
  overflow: hidden;
  transition: transform 0.5s ease;
}

.mode-toggle .toggle #dark-mode {
  position: relative;
  width: 100%;
  height: 100%;
  overflow: hidden;
  border-radius: 50%;
}

.mode-toggle .toggle #dark-mode:before {
  content: "";
  position: relative;
  width: 100%;
  height: 100%;
  left: 50%;
  float: left;
  background-color: #a5abba;
  transition: border-radius 0.5s ease,
    width 0.5s ease, height 0.5s ease, left 0.5s ease, transform 0.5s ease;
}

h1,
h2 {
  font-weight: normal;
}

#main {
  padding: 0em 0 6em 0;
}

#wrapper>*>.inner {
  width: 100%;
  max-width: 68em;
  margin: 0 auto;
  padding: 0 2.5em;
}

button {
  border: none;
  background: #ed4652;
  color: #fff;
  text-transform: uppercase;
  font-size: 1.25em;
  padding: 10px 20px;
  border-radius: 10px;
  cursor: pointer;
  box-shadow: 0 1px 5px rgba(68, 68, 68, 0.5);
}

button.greenBtn {
  background: #00c722;
}

article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
menu,
nav,
section {
  display: block;
}

*+.tiles {
  margin-top: 2em;
}

.tiles {
  display: -moz-flex;
  display: -webkit-flex;
  display: -ms-flex;
  display: flex;
  -moz-flex-wrap: wrap;
  -webkit-flex-wrap: wrap;
  -ms-flex-wrap: wrap;
  flex-wrap: wrap;
  position: relative;
}

.tiles article {
  -moz-transition: -moz-transform 0.5s ease, opacity 0.5s ease;
  -webkit-transition: -webkit-transform 0.5s ease, opacity 0.5s ease;
  -ms-transition: -ms-transform 0.5s ease, opacity 0.5s ease;
  transition: transform 0.5s ease, opacity 0.5s ease;
  position: relative;
  width: calc(33.33333%);
}

.tiles article>.image {
  -moz-transition: -moz-transform 0.5s ease;
  -webkit-transition: -webkit-transform 0.5s ease;
  -ms-transition: -ms-transform 0.5s ease;
  transition: transform 0.5s ease;
  position: relative;
  display: block;
  width: 100%;
  border-radius: 4px;
  overflow: hidden;
}

.image {
  border-radius: 4px;
  border: 0;
  display: inline-block;
  position: relative;
}

.tiles article>a {
  display: -moz-flex;
  display: -webkit-flex;
  display: -ms-flex;
  display: flex;
  -moz-flex-direction: column;
  -webkit-flex-direction: column;
  -ms-flex-direction: column;
  flex-direction: column;
  -moz-align-items: center;
  -webkit-align-items: center;
  -ms-align-items: center;
  align-items: center;
  -moz-justify-content: center;
  -webkit-justify-content: center;
  -ms-justify-content: center;
  justify-content: center;
  -moz-transition: background-color 0.5s ease, -moz-transform 0.5s ease;
  -webkit-transition: background-color 0.5s ease, -webkit-transform 0.5s ease;
  -ms-transition: background-color 0.5s ease, -ms-transform 0.5s ease;
  transition: background-color 0.5s ease, transform 0.5s ease;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  padding: 1em;
  border-radius: 4px;
  border-bottom: 0;
  color: #ffffff;
  text-align: center;
  text-decoration: none;
  z-index: 3;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
