<template>
  <div class="home">
    <b-container class="bv-example-row header">
      <b-row>
        <h1>Title</h1>
      </b-row>
      <b-row>
        <!-- <h5>Select your preferences to find your perfect cookie recipe</h5> -->
        <h5>Subheader content</h5>
      </b-row>
    </b-container>

    <div id="form">
      <b-container class="bv-example-row">
        <b-row>
          <b-col cols="4" class="card" v-for="(category, index) in categories">
            <div v-for="option in category.options">
              <label>
                <div>
                  <b-img src="https://spaceholder.cc/200x200"> </b-img>
                  <input
                    type="radio"
                    :name="category.id"
                    v-bind:value="option.value"
                    v-model="results[index]"
                  />
                  <span>{{ option.label }}</span>
                </div>
              </label>
            </div>

            <div>
              <h3>{{ category.name }}</h3>
              <h4>{{ category.description }}</h4>
            </div>
          </b-col>
        </b-row>

        <b-row>
          <b-col class="recipe"> {{ spreadResult }} {{ biteResult }} </b-col>
        </b-row>
      </b-container>
    </div>
  </div>
</template>

<style scoped>
.header {
  text-align: center;
  padding: 20px;
  margin-top: 30px;
}

h3 {
  font-size: 20px;
}

h4 {
  font-size: 14px;
}

#form {
  display: flex;
  flex-direction: row;
  padding: 30px;
  background-color: #aaaaaa;
}

input[type="radio"] {
  display: none;
}

.card {
  padding: 30px;
}

label {
  display: flex;
  flex-direction: row;
}

.this {
  background-color: green;
}

span {
  border: 2px solid #bbbbbb;
  /* background: #8eacd4; */
  padding: 10px;
}

.cardRow .cardBtn input:checked + span {
  background: #8eacd4;
  border: 2px solid #777777;
}

.cardRow .cardBtn input + span {
  color: #eee;
}
</style>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
export default {
  name: "Home",
  data() {
    return {
      categories: [
        {
          name: "Tenderness",
          id: "tenderness",
          description:
            "Heirloom biodiesel quinoa mlkshk asymmetrical master cleanse affogato blog marfa chillwave semiotics gastropub",
          imgUrl: "",
          options: [
            {
              label: "Crunchy",
              value: "crunchy",
              imgUrl: "",
            },
            {
              label: "Soft",
              value: "soft",
              imgUrl: "",
            },
          ],
        },
        {
          name: "Rise",
          id: "rise",
          description:
            "Offal waistcoat occupy humblebrag pinterest, pour-over food truck bitters.",
          imgUrl: "",
          options: [
            {
              label: "Thick",
              value: "thick",
              imgUrl: "",
            },
            {
              label: "Thin",
              value: "thin",
              imgUrl: "../src/assets/images/Cookies-10.png",
            },
          ],
        },
        {
          name: "Texture",
          id: "texture",
          description: "Banjo flannel pour-over fixie twee humblebrag.",
          imgUrl: "",
          options: [
            {
              label: "Fudgy",
              value: "fudgy",
              imgUrl: "",
            },
            {
              label: "Cakey",
              value: "cakey",
              imgUrl: "",
            },
          ],
        },
        {
          name: "Chocolate",
          id: "chocolate",
          description:
            "Mixtape edison bulb tattooed blog, brunch seitan live-edge plaid forage",
          imgUrl: "",
          options: [
            {
              label: "Small Chunks",
              value: "small",
              imgUrl: "",
            },
            {
              label: "Large Chunks",
              value: "large",
              imgUrl: "",
            },
            {
              label: "Swirled In",
              value: "swirled",
              imgUrl: "",
            },
          ],
        },
        {
          name: "Flavor",
          id: "flavor",
          description: "Sartorial single-origin coffee VHS green juice salvia.",
          imgUrl: "",
          options: [
            {
              label: "Dark, toffee",
              value: "dark",
              imgUrl: "",
            },
            {
              label: "Light, milky",
              value: "light",
              imgUrl: "",
            },
          ],
        },
      ],
      results: [],
    };
  },
  computed: {
    spreadResult() {
      return this.results;
    },
    // biteResult() {
    //     return this.results[1]
    // }
  },
  methods: {
    onDeleteLastItem() {
      this.exampleList.pop();
    },
  },
  components: {
    HelloWorld,
  },
};
</script>
