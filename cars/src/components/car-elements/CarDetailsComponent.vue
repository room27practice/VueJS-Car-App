<template>
  <div class="card mx-2" style="width: 18rem"  v-bind:class="{dimmed :!info.isChosen}" >
    <img :src="info.imgUrl" class="card-img-top" alt="audi" />
    <div class="card-body">
      <p class="card-text">
        <span class="my-text">{{ info.title }}</span
        >{{ info.mainTxt }}
        <span v-if="!textMore"
          >...<span @click="textMore = true" class="click-able"
            >show more</span
          ></span
        >
        <span v-if="textMore"
          >{{ info.additionalText }}
          <span class="click-able" @click="textMore = false">show less</span>
        </span>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      textMore: false,
    };
  },

  props: {
    info: {
      id:Number,
      isChosen: Boolean,
      imgUrl: String,
      title: String,
      mainTxt: String,
      additionalText: String,
    },
  },

  // methods:
};
</script>
<style scoped>
.my-text {
  color: yellow;
  background-color: black;
}

.click-able {
  cursor: pointer;
}

.click-able:hover {
  font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
  color: orangered;
}

div.card {
  border-radius: 1rem;
  border: 2px solid darkgreen; 
}

div.card img {
  border-radius: 1rem 1rem 0 0;
  height: 11rem;
}

.dimmed{
 opacity: 50%;
}

/* div.selected {
  opacity: 100%;
} */
</style>