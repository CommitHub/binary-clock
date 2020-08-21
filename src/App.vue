<template>
  <div
    id="app"
    class="flex flex-col px-4 pt-12 pb-16 content-between min-h-screen"
  >
    <div class="mx-auto">
      <h1 class="text-gray-700 font-bold text-4xl text-center leading-tight">
        Binary Clock
      </h1>
    </div>
    <div class="mx-auto flex flex-1 py-8">
      <div class="flex my-auto items-end">
        <!-- Bits Hour -->
        <div class="flex flex-col items-center mr-3">
          <span
            class="bit bg-gray-400"
            :class="{ 'bg-red-500': bitsValues.H[2] == 1 }"
          >
            2
          </span>
          <span
            class="bit bg-gray-400"
            :class="{ 'bg-red-500': bitsValues.H[3] == 1 }"
          >
            1
          </span>
          <span
            class="text-red-500 w-8 font-bold text-center text-5xl leading-tight"
          >
            {{ timeValues.H }}
          </span>
          <span class="text-red-500 w-8 text-center text-xs leading-tight">
            {{ bitsValues.H }}
          </span>
        </div>
        <div class="flex flex-col items-center mx-3">
          <span
            class="bit bg-gray-400"
            :class="{ 'bg-red-400': bitsValues.h[0] == 1 }"
          >
            8
          </span>
          <span
            class="bit bg-gray-400"
            :class="{ 'bg-red-400': bitsValues.h[1] == 1 }"
          >
            4
          </span>
          <span
            class="bit bg-gray-400"
            :class="{ 'bg-red-400': bitsValues.h[2] == 1 }"
          >
            2
          </span>
          <span
            class="bit bg-gray-400"
            :class="{ 'bg-red-400': bitsValues.h[3] == 1 }"
          >
            1
          </span>
          <span
            class="text-red-400 w-8 font-bold text-center text-5xl leading-tight"
          >
            {{ timeValues.h }}
          </span>
          <span class="text-red-400 w-8 text-center text-xs leading-tight">
            {{ bitsValues.h }}
          </span>
        </div>
        <div class="w-3 mb-5">
          <span
            class="text-gray-300 font-bold text-center text-5xl leading-tight"
          >
            :
          </span>
        </div>
        <!-- Bits Minutes -->
        <div class="flex flex-col items-center mx-3">
          <span
            class="bit bg-gray-400"
            :class="{ 'bg-teal-500': bitsValues.M[1] == 1 }"
          >
            4
          </span>
          <span
            class="bit bg-gray-400"
            :class="{ 'bg-teal-500': bitsValues.M[2] == 1 }"
          >
            2
          </span>
          <span
            class="bit bg-gray-400"
            :class="{ 'bg-teal-500': bitsValues.M[3] == 1 }"
          >
            1
          </span>
          <span
            class="text-teal-500 w-8 font-bold text-center text-5xl leading-tight"
          >
            {{ timeValues.M }}
          </span>
          <span class="text-teal-500 w-8 text-center text-xs leading-tight">
            {{ bitsValues.M }}
          </span>
        </div>
        <div class="flex flex-col items-center mx-3">
          <span
            class="bit bg-gray-400"
            :class="{ 'bg-teal-400': bitsValues.m[0] == 1 }"
          >
            8
          </span>
          <span
            class="bit bg-gray-400"
            :class="{ 'bg-teal-400': bitsValues.m[1] == 1 }"
          >
            4
          </span>
          <span
            class="bit bg-gray-400"
            :class="{ 'bg-teal-400': bitsValues.m[2] == 1 }"
          >
            2
          </span>
          <span
            class="bit bg-gray-400"
            :class="{ 'bg-teal-400': bitsValues.m[3] == 1 }"
          >
            1
          </span>
          <span
            class="text-teal-400 w-8 font-bold text-center text-5xl leading-tight"
          >
            {{ timeValues.m }}
          </span>
          <span class="text-teal-400 w-8 text-center text-xs leading-tight">
            {{ bitsValues.m }}
          </span>
        </div>
        <div class="w-3 mb-5">
          <span
            class="text-gray-300 font-bold text-center text-5xl leading-tight"
          >
            :
          </span>
        </div>
        <!-- Bits Seconds -->
        <div class="flex flex-col items-center mx-3">
          <span
            class="bit bg-gray-400"
            :class="{ 'bg-blue-500': bitsValues.S[1] == 1 }"
          >
            4
          </span>
          <span
            class="bit bg-gray-400"
            :class="{ 'bg-blue-500': bitsValues.S[2] == 1 }"
          >
            2
          </span>
          <span
            class="bit bg-gray-400"
            :class="{ 'bg-blue-500': bitsValues.S[3] == 1 }"
          >
            1
          </span>
          <span
            class="text-blue-500 w-8 font-bold text-center text-5xl leading-tight"
          >
            {{ timeValues.S }}
          </span>
          <span class="text-blue-500 w-8 text-center text-xs leading-tight">
            {{ bitsValues.S }}
          </span>
        </div>
        <div class="flex flex-col items-center ml-3">
          <span
            class="bit bg-gray-400"
            :class="{ 'bg-blue-400': bitsValues.s[0] == 1 }"
          >
            8
          </span>
          <span
            class="bit bg-gray-400"
            :class="{ 'bg-blue-400': bitsValues.s[1] == 1 }"
          >
            4
          </span>
          <span
            class="bit bg-gray-400"
            :class="{ 'bg-blue-400': bitsValues.s[2] == 1 }"
          >
            2
          </span>
          <span
            class="bit bg-gray-400"
            :class="{ 'bg-blue-400': bitsValues.s[3] == 1 }"
          >
            1
          </span>
          <span
            class="text-blue-400 w-8 font-bold text-center text-5xl leading-tight"
          >
            {{ timeValues.s }}
          </span>
          <span class="text-blue-400 w-8 text-center text-xs leading-tight">
            {{ bitsValues.s }}
          </span>
        </div>
      </div>
    </div>
    <div class="mx-auto">
      <h2 class="text-gray-700 font-bold text-2xl text-center leading-tight">
        Made with 💖 by
        <a href="https://commithub.com" target="_blank" rel="noopener">
          CommitHub
        </a>
      </h2>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data: function() {
    return {
      timeValues: {
        H: "",
        h: "",
        M: "",
        m: "",
        S: "",
        s: ""
      }
    };
  },
  mounted() {
    setInterval(() => {
      this.handleDateValues(new Date(Date.now()));
    }, 500);
  },
  methods: {
    handleDateValues(dateObj) {
      let time = dateObj
        .toTimeString()
        .split(" ")[0]
        .split(":");
      this.timeValues.H = time[0][0];
      this.timeValues.h = time[0][1];
      this.timeValues.M = time[1][0];
      this.timeValues.m = time[1][1];
      this.timeValues.S = time[2][0];
      this.timeValues.s = time[2][1];
    },
    parseBits(value) {
      return ("0000" + parseInt(value).toString(2)).slice(-4);
    }
  },
  computed: {
    bitsValues() {
      return {
        H: this.parseBits(this.timeValues.H),
        h: this.parseBits(this.timeValues.h),
        M: this.parseBits(this.timeValues.M),
        m: this.parseBits(this.timeValues.m),
        S: this.parseBits(this.timeValues.S),
        s: this.parseBits(this.timeValues.s)
      };
    }
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Arvo&display=swap");
@tailwind base;
@tailwind components;
@tailwind utilities;

#app {
  font-family: "Arvo", serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #1b262c;
  font-size: 1.3em;
  word-spacing: 1px;

  @media (max-width: $desktop-sm) {
    font-size: 1em;
  }
}

p {
  line-height: 1.6;
}

.bit {
  @apply rounded-md h-8 w-8 text-lg leading-8 text-center align-middle mb-3 text-gray-400;
  color: rgb(255, 255, 255, 0.15);
}
</style>
