<template>
  <div class="home">

    <!-- <hello-world /> -->

    <div id ="form">

          <div v-for="(category, index) in categories">
            <h3>{{ category.name }}</h3>
            <h4>{{ category.description }}</h4>

              <div v-for="option in category.options">
                <input type="radio" :name="category.id" id="one" v-bind:value="option.value" v-model="results[index]">
                <label for="one">{{ option.label }}</label>
            </div>
          </div>
    </div>

      {{ results }}
      {{ biteResult }}
    </div>


  </div> 
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  data () {
    return {
      categories: [
        {
          name: 'Spread',
          id: 'spread',
          description: 'The way a cookie expands and settles while baking',
          options: [
            {
              label: "Wide",
              value: "Wide",
              imgUrl: "cookieproject/src/components/HelloWorld.vue"
            },
            {
              label: "Compact",
              value: "Compact",
              imgUrl: ""
            }, 
            {
              label: "Test",
              value: "Test",
              imgUrl: ""
            }
          ],
        },
        {
          name: 'Bite',
          id: 'bite',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
          imgUrl: "",
          options: [
            {
              label: "Crunchy",
              value: "Crunchy",
              imgUrl: ""
            },
            {
              label: "Compact",
              value: "compact",
              imgUrl: ""
            },
          ],
        },
      ],
      results: [

      ]
    }
  }, 
  computed: {
    biteResult(){
      return this.results[1]
    }
  },
  methods:{
    onDeleteLastItem(){
      this.exampleList.pop();
    }
  },
  components: {
    HelloWorld
  },

};
</script>

<style scoped>
.home {
  background-color: lightgoldenrodyellow;
  padding: 20px;
}

.home .hello{
  background-color: darkgray;
}
</style>