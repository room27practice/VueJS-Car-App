<template>
  <div class="hello">
    <div class="main-pic-container">
      <h1 v-if="!imgSelected">{{ msg }}</h1>
      <img
        class="main-pic"
        v-if="imgSelected"
        :src="imgSelected"
        alt="chosenCar"
      />
    </div>

    <h3>Automobile Brands:</h3>
    <div class="px-4 d-flex">
      <CarDet
        v-for="(car, index) in carArticles"
        :key="index"
        v-bind:info="car"
        v-on:choose="setCard"
      />
    </div>
  </div>
</template>

<script>
import CarDet from "./car-elements/CarDetailsComponent.vue";

export default {
  name: "HelloWorld",
  data: function () {
    return {
      imgSelected: "",
      carArticles: [
        {
          id: 1,
          title: "Audi",
          isChosen: false,
          imgUrl:
            "https://media.istockphoto.com/photos/audi-a3-quattro-steering-wheel-picture-id157728351",
          mainTxt: ` The name is based on the Latin
        translation of the surname of the founder , August Horch. Horch, meaning
        "listen" in German, becomes audi in Latin`,
          additionalText: `The four rings of the Audi logo each represent one of four car
          companies that banded together to create Audi's predecessor company,
          Auto Union. Audi's slogan is Vorsprung durch Technik, meaning "Being
          Ahead through Technology". Audi, along with fellow German marques BMW
          and Mercedes-Benz, is among the best-selling luxury automobile brands
          in the world.`,
        },
        {
          id: 2,
          title: "Mercedes",
          isChosen: false,
          imgUrl:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/2/2e/Mercedes_Benz_Classe_S_dsc06455.jpg/1024px-Mercedes_Benz_Classe_S_dsc06455.jpg",
          mainTxt: ` Мерцедес-Бенц (немско произношение mɛʁˈtseːdəs ˈbɛnts) е търговска марка за производство на автомобили`,
          additionalText: `камиони, автобуси, двигатели и други, създадена от компанията „Даймлер-Бенц“ (Daimler-Benz AG), сега собственост на концерна „Даймлер“ (Daimler AG).`,
        },
        {
          id: 3,
          title: "Buggatti",
          isChosen: false,
          imgUrl:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/c/c9/Bugatti_Veyron_16.4_%E2%80%93_Frontansicht_%281%29%2C_5._April_2012%2C_D%C3%BCsseldorf.jpg/1200px-Bugatti_Veyron_16.4_%E2%80%93_Frontansicht_%281%29%2C_5._April_2012%2C_D%C3%BCsseldorf.jpg",
          mainTxt: ` Bugatti Veyron е хиперкола на компанията Bugatti, произвеждана от 2005 до 2015 г. Наречена е в чест на френския състезател Пиер Вейрон, победител от 1939 г. в състезанието 24 часа на Льо Ман`,
          additionalText: `През 2010 г. списанията Top Gear и Robb Report присъждат наградата „Автомобил на десетилетието“ на Bugatti Veyron и неговата модификация Grand Sport, съответно[2]. Модификацията Super Sport през 2010 г. подобрява световния рекорд за скорост и става най-бързия сериен автомобил в света. Производството на Veyron към момента е приключено, общо са продадени 450 автомобила: 300 купе и 150 роудстъри.`,
        },
        {
          id: 4,
          title: "Pagani Zonda",
          isChosen: false,
          imgUrl:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/0/0f/Pagani_Zonda_PS_Front.jpg/1200px-Pagani_Zonda_PS_Front.jpg",
          mainTxt: ` Спортен автомобил със средноразположен двигател, произвеждан от Пагани от 1999 година в Италия. Годишно се произвеждат 17 – 19 автомобила от този модел.`,
          additionalText: `Към юни 2009 година са проиведени 106 коли, някои от които тестови, като версиите са две: двуместно купе и роудстър. Конструкцията на автомобилите е предимно от карбонови нишки. Някои от по-ранните конструкции са направени от шампиона във Формула 1 Хуан Мануел Фанджо. Първоначално автомобилите е трябвало да бъдат наречени „Фанджо Ф1“, но след смъртта му през 1995 година са преименувани на Зонда, което е местното название на вятъра фьон в Аржентина – „viento sonda“.`,
        },
      ],
    };
  },

  props: {
    msg: String,
  },
  components: {
    CarDet,
  },

  methods: {
    setCard: function (ev, id) {
      console.log(id);
      console.log(ev);
      for (let i = 0; i < this.carArticles.length; i++) {
        let current = this.carArticles[i];
        if (id == current.id) {
          current.isChosen = true;
          this.imgSelected = current.imgUrl;
        } else {
          current.isChosen = false;
        }
      }
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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

div.main-pic-container{
  height: 30rem;
}
img.main-pic {
  max-height: 28rem;
  width:auto;
  border-radius: 2rem;
}
</style>
