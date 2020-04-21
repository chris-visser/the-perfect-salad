<template>
  <section class="section">
    <div class="text-center">
      <b-button @click="randomize">Hussle my lattice, bro</b-button>
    </div>
    <ul>
      <li v-for="{ title, items } in categories" :key="title">
        <img :src="items[0].image" :alt="items[0].title">
        <div class="item-body">
          <strong>{{ title }}</strong><br />
          {{ items[0].title }}
        </div>
      </li>
    </ul>
  </section>
</template>

<script>
import Card from '~/components/Card'

function shuffle(array) {
  var currentIndex = array.length, temporaryValue, randomIndex

  // While there remain elements to shuffle...
  while (0 !== currentIndex) {

    // Pick a remaining element...
    randomIndex = Math.floor(Math.random() * currentIndex)
    currentIndex -= 1

    // And swap it with the current element.
    temporaryValue = array[currentIndex]
    array[currentIndex] = array[randomIndex]
    array[randomIndex] = temporaryValue
  }

  return array
}


export default {
  name: 'HomePage',

  components: {
    Card
  },

  data() {
    return {
      categories: this.shuffleItems([{
        title: 'Base',
        items: [{
          title: 'Lettuce',
          image: '/lettuce.webp'
        }, {
          title: 'Spinach',
          image: '/spinach.jfif'
        }, {
          title: 'Kale',
          image: '/kale.jfif'
        }, {
          title: 'Chard',
          image: '/chard.jfif'
        }, {
          title: 'Collards',
          image: '/collards.webp'
        }, {
          title: 'Arugula',
          image: '/arugula.jfif'
        }, {
          title: 'Pea Shoots',
          image: '/pea-shoots.jpeg'
        }, {
          title: 'Cabbage',
          image: '/cabbage.png'
        }]
      }, {
        title: 'Crunchy Stuff',
        items: [{
          title: 'Carrots',
          image: '/carrots.png'
        }, {
          title: 'Sprouts',
          image: '/sprouds.png'
        }, {
          title: 'Cucumber',
          image: '/cucumber.jfif'
        }, {
          title: 'Croutons',
          image: '/croutons.jfif'
        }, {
          title: 'Zucchini',
          image: '/zucchini.jfif'
        }, {
          title: 'Bell Pepper',
          image: '/bell-pepper.jfif'
        }, {
          title: 'Apple',
          image: '/apple.jfif'
        }, {
          title: 'Seeds & Nuts',
          image: '/seeds.jfif'
        }]
      }, {
        title: 'Something Soft',
        items: [{
          title: 'Roasted Sweet Potatoes',
          image: '/sweet-potatoes.jpg'
        }, {
          title: 'Cheese',
          image: '/cheese.jfif'
        }, {
          title: 'Avocado',
          image: '/avocado.jfif'
        }, {
          title: 'Tomatoes',
          image: '/tomatoes.jfif'
        }, {
          title: 'Rice',
          image: '/rice.jpg'
        }, {
          title: 'Olives',
          image: '/olives.jfif'
        }]
      }, {
        title: 'The Unexpected',
        items: [{
          title: 'Watermelon Cubes',
          image: '/watermelon-cubes.jfif'
        }, {
          title: 'Cottage Cheese',
          image: '/cottage-cheese.jpg'
        }, {
          title: 'Hummus',
          image: '/hummus.jpg'
        }, {
          title: 'Bacon',
          image: '/bacon.jfif'
        }, {
          title: 'Pickled Veggies',
          image: '/pickled-veggies.jpg'
        }, {
          title: 'Herbs',
          image: '/herbs.jfif'
        }]
      }, {
        title: 'Protein',
        items: [{
          title: 'Beans',
          image: '/beans.jfif'
        }, {
          title: 'Eggs',
          image: '/eggs.jfif'
        }, {
          title: 'Tuna',
          image: '/tuna.jfif'
        }, {
          title: 'Chicken',
          image: '/chicken.'
        }, {
          title: 'Steak'
        }, {
          title: 'Tofu'
        }, {
          title: 'Peas'
        }, {
          title: 'Quinoa'
        }, {
          title: 'Nuts'
        }]
      }, {
        title: 'Dressing',
        items: [{
          title: 'Mustard-based'
        }, {
          title: 'Tahini-based'
        }, {
          title: 'Dairy-based'
        }, {
          title: 'Vinaigrette'
        }, {
          title: 'Pesto-based'
        }, {
          title: 'Fruity'
        }]
      }])
    }
  },
  methods: {
    shuffleItems(categories) {
      return categories.map(({ title, items }) => ({
        title,
        items: shuffle(items)
      }))
    },
    randomize() {
      this.categories = this.shuffleItems(this.categories)
    }
  }
}
</script>

<style>
ul {
  list-style: none;
  width: 100%;
  border-top: 1px solid #cccccc;
}
li {
  padding: 10px;
  margin-bottom: 10px;
  display: flex;
  align-items: center;
}
img {
  margin-right: 20px;
  border: 1px solid #cccccc;
  height: 60px;
  width: 60px;
}
button {
  margin-bottom: 30px;
}
</style>
