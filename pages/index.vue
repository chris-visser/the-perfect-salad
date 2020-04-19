<template>
  <section class="section">
    <div class="columns is-mobile">
      <card v-for="{ title, items } in categories" :key="title" :title="title" icon="foo">
        {{ items[0].title }}
      </card>
    </div>
    <div class="text-center">
      <b-button @click="randomize">Try again</b-button>
    </div>
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
          title: 'Lettuce'
        }, {
          title: 'Spinach'
        }, {
          title: 'Kale'
        }, {
          title: 'Chard'
        }, {
          title: 'Collards'
        }, {
          title: 'Arugula'
        }, {
          title: 'Pea Shoots'
        }, {
          title: 'Cabbage'
        }]
      }, {
        title: 'Crunchy Stuff',
        items: [{
          title: 'Carrots'
        }, {
          title: 'Sprouts'
        }, {
          title: 'Cucumber'
        }, {
          title: 'Croutons'
        }, {
          title: 'Zucchini'
        }, {
          title: 'Bell Pepper'
        }, {
          title: 'Apple'
        }, {
          title: 'Seeds'
        }]
      }, {
        title: 'Something Soft',
        items: [{
          title: 'Roasted Sweet Potatoes'
        }, {
          title: 'Cheese'
        }, {
          title: 'Avocado'
        }, {
          title: 'Tomatoes'
        }, {
          title: 'Rice'
        }, {
          title: 'Olives'
        }]
      }, {
        title: 'The Unexpected',
        items: [{
          title: 'Watermelon Cubes'
        }, {
          title: 'Cottage Cheese'
        }, {
          title: 'Hummus'
        }, {
          title: 'Bacon'
        }, {
          title: 'Pickled Veggies'
        }, {
          title: 'Herbs'
        }]
      }, {
        title: 'Protein',
        items: [{
          title: 'Beans'
        }, {
          title: 'Eggs'
        }, {
          title: 'Tuna'
        }, {
          title: 'Chicken'
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
.card-header {
  height: 72px;
}
.card-footer-item {
  height: 72px;
}
</style>
