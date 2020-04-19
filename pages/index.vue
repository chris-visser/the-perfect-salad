<template>
  <section class="section">
    <div v-for="{ title, items } in categories" :key="title" class="columns is-mobile">
      <card>
        {{ items[0].title }}
      </card>
    </div>
  </section>
</template>

<script>
import Card from '~/components/Card'

function shuffle(array) {
  var currentIndex = array.length, temporaryValue, randomIndex;

  // While there remain elements to shuffle...
  while (0 !== currentIndex) {

    // Pick a remaining element...
    randomIndex = Math.floor(Math.random() * currentIndex);
    currentIndex -= 1;

    // And swap it with the current element.
    temporaryValue = array[currentIndex];
    array[currentIndex] = array[randomIndex];
    array[randomIndex] = temporaryValue;
  }

  return array;
}


export default {
  name: 'HomePage',

  components: {
    Card
  },

  data() {
    return {
      categories: [{
        title: 'Base',
        items: shuffle([{
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
        }])
      }, {
        title: 'Something Crunchy',
        items: shuffle([{
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
        }])
      }, {
        title: 'Something Soft',
        items: shuffle([{
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
        }])
      }, {
        title: 'Something Unexpected',
        items: shuffle([{
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
        }])
      }, {
        title: 'Protein',
        items: shuffle([{
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
        }])
      }, {
        title: 'Dressing',
        items: shuffle([{
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
        }])
      }]
    }
  }
}
</script>
