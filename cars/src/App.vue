<template>
  <div id="app">
    <img
      v-bind:class="{ hidden: isLogoHidden }"
      alt="Vue logo"
      src="./assets/logo.png"
      v-on:click="visualiseHello"
    />
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <!-- <img src="https://media.istockphoto.com/photos/friends-red-cat-and-corgi-dog-walking-in-a-summer-meadow-under-the-picture-id1324099927"/>
     <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Numquam deserunt illo eos. Impedit cumque eveniet ab similique officiis alias aliquid voluptatibus, architecto ad blanditiis omnis id quis quidem ex commodi!</p> -->
    <HelloWorld msg="11A klas" />

    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Est aliquam
      architecto, optio quam corrupti cum nam dignissimos asperiores ex quae
      quisquam animi reiciendis, itaque recusandae quaerat, ducimus accusamus
      sit similique!

      <span v-if="!isLogoHidden" class="mag"
        >Lorem ipsum dolor sit amet consectetur adipisicing elit. Eveniet illum
        cum nisi ipsam quaerat aspernatur veniam dignissimos praesentium
        sapiente unde soluta eum, explicabo magni asperiores consectetur aliquid
        quibusdam. Placeat, architecto. Lorem ipsum dolor, sit amet consectetur
        adipisicing elit. Repellendus laboriosam ad cupiditate porro doloribus
        quod maiores sequi, dolores repudiandae perferendis deleniti quaerat
        quos non aspernatur eveniet aut est laborum aliquid. Lorem ipsum dolor
        sit amet consectetur adipisicing elit. Doloribus iste consequatur fugit
        minus exercitationem tempore aut, ut placeat veniam laborum, beatae
        possimus explicabo accusantium nulla facilis id alias eligendi
        libero!</span
      >
    </p>
    <input
      type="submit"
      value="Hide Logo"
      class="btn btn-primary"
      @click="isLogoHidden = !isLogoHidden"
    />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  data: function () {
    return {
      isLogoHidden: false,
    };
  },
  name: "App",
  components: {
    HelloWorld,
  },
  methods: {
    visualiseHello: function () {
      alert("Hello");
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.hidden {
  display: none;
}
.mag {
  color: magenta;
}
</style>
