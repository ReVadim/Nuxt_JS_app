<template>
  <div>
    <transition-group name="fade" tag="div">
      <div v-for="i in [currentIndex]" :key="i">
        <img :src="currentImg" />
        <a class="prev" @click="prev" href="#">&#10094; Previous</a>
        <a class="next" @click="next" href="#">&#10095; Next</a>
      </div>
    </transition-group>

  </div>
</template>
<script>
export default {
  name: "Image_slider",
  data() {
    return {
      images: [
        "https://boobles.ru/wp-content/uploads/2019/10/samyj-vkusnyj-zavtrak-foto.jpg",
        "https://mindmotivationaudio.com/wp-content/uploads/2019/07/breakfast-e1486530235445-Copy.jpg",
        "https://static-sl.insales.ru/files/1/4388/6803748/original/Still-life_Blueberries_497940.jpg",
        "https://speisekarte.menu/storage/media/company_images/1232943/random1920780417.jpg",
        "https://celiakia.pl/wp-content/uploads/2013/01/warzywa.jpg"
      ],
      timer: null,
      currentIndex: 0
    };
  },


  methods: {

    next: function() {
      this.currentIndex += 1;
    },
    prev: function() {
      this.currentIndex -= 1;
    }
  },

  computed: {
    currentImg: function() {
      return this.images[Math.abs(this.currentIndex) % this.images.length];
    }
  }
};
</script>
