<template>
  <section id="top" class="pt-28 md:pt-40 md:h-screen flex lg:pb-20 pb-10">
    <!-- movie hero main container -->
    <div class="flex flex-col w-full justify-center">
      <div class="text-2xl md:text-3xl text-center p-4 lg:p-8">
        <div class="max-w-screen-lg text-left mx-auto">
          <div class="w-1/2 text-4xl title">
            Now streaming blockbuster movies, epic originals, and addictive
            series
            <div class="text-xl mt-4">Plans start at $9.99/month</div>
            <button
              class="btn btn-outline rounded-full border-2 px-8 py-1 my-4"
            >
              sign up now
            </button>
          </div>
        </div>
      </div>
      <!-- movie tile conveyor belt container -->
      <div class="conveyor-belts overflow-hidden">
        <div id="tray-1" class="w-full mb-3 flex gap-3 -ml-28">
          <!-- movie tiles tray one -->
          <img
            v-for="pic in trayPics1"
            :src="`./images/tiles/${pic}`"
            class="w-48 md:w-96"
          />
        </div>
        <!-- movie tile conveyor belt tray two -->
        <div id="tray-2" class="w-full mb-3 flex gap-3">
          <!-- movie tiles tray two -->
          <img
            v-for="pic in trayPics2"
            :src="`./images/tiles/${pic}`"
            class="w-48 md:w-96"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import gsap from "gsap";

import { trayPics1, trayPics2 } from "~/constants/";

export default {
  mounted() {
    this.scrollTrays();
  },

  data() {
    return {
      trayPics1: trayPics1,
      trayPics2: trayPics2,
    };
  },
  methods: {
    scrollTrays() {
      gsap.to("#tray-1", {
        x: -10500,
        duration: 228,
        ease: "linear",
        repeat: -1,
      });
      gsap.to("#tray-2", {
        x: -10500,
        duration: 168,
        ease: "linear",
        repeat: -1,
      });
    },
  },
};
</script>

<style>
#top {
  background: url("/images/house-of-the-dragon-bg-v4.webp");
  background-size: cover;
  background-position: center top;
  background-repeat: no-repeat;
}
</style>
