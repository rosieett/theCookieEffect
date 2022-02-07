<template>
  <div class="home">

    <!-- <hello-world /> -->

    <div id ="form">
        <h3>Question 1</h3>

          <div v-for="category in categories">
          <h3>{{ category.name }}</h3>
            <h4>{{ category.description }}</h4>

          <div v-for="options in categories">
            <input type="radio" name="name" id="one" v-bind:value="categories.value" v-model="categories.name">
            <label for="one">{{ options.label }}</label>
        </div>
      </div>

      <div>
        <h3>User Selections</h3>
        <div>
          Spread: {{ categories.value }}
        </div>
      </div>
      </div>
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
          description: 'The way a cookie exapnds and settles while baking',
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
            }
          ],
        },
        {
          name: 'Bite',
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
      ]
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