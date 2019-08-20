<template>
  <div id="container" style="width=50%">
    <div id="image-container">
      <img :src="imageSrc(this.activeImage)">
    </div>
    <div style="text-align:center">
      <button type="button" v-on:click="switchImage()"><div class="before"></div><div class="after">❯</div>Screenshots of MeetWorth</button> 
    </div>
   </div>
</template>

<script>

export default {
  name: 'image-slider:',
  props: {
    initialImage: String,
    images: Array
  },
  data() {
    return {
      activeImage: this.initialImage,
      index: this.images.indexOf(this.activeImage)
    };
  },
  methods: {
    imageSrc(imageName) {
      return require('../assets/' + imageName +'.jpg');
    },

    switchImage() {
      if (this.index < this.images.length - 1) {
        ++this.index
      }
      else {
        this.index = 0;
      }
      this.activeImage = this.images[this.index];
    }
  }
};
</script>

<style scoped>
button {
    padding: 1vw;
    color: #ffffff;
    background: green;
    border: 0;
    position: relative;
    padding-right: 8vw;
}
button .before {
    content: '';
    width: 4vw;
    position: absolute;
    right: 0;
    top: 0;
    bottom: 0;
    background: white;
    border: 1px solid green;
}
button .after {
    content: '❯';
    position: absolute;
    right: 2vw;
    color: green;
}

#image-container {
  height: 450px;
}
img {
  object-fit: scale-down;
}
</style>
