<template>
  <div>
    <Navbar />
    <Image_slider />
      <Nuxt />
    <Footer />
  </div>
</template>


<script>
import Navbar from "~/components/Navbar";
import Image_slider from "~/components/Image_slider";
import Footer from "~/components/Footer";

export default {
  components: {
    Footer,
    Image_slider,
    Navbar,
  }
};
</script>

<style>

</style>
