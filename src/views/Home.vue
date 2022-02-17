<template>
<div class="home">

    <b-container class="bv-example-row header">
        <b-row>
            <h1>The Cookie Effect</h1>
        </b-row>
        <b-row>
            <h5>Select your preferences to find your perfect cookie recipe</h5>
        </b-row>
    </b-container>

    <div id="form">

        <b-container class="bv-example-row">
            <b-row>
                <b-col>
                    <div class="cardRow" v-for="(category, index) in categories">

                        <div class="panel">
                            <div class="text">
                            <h3>{{ category.name }}</h3>
                            <h4>{{ category.description }}</h4>
                            </div>
                            <div class="cardBtn" v-for="option in category.options">

                                <input type="radio" :name="category.id" id="one" v-bind:value="option.value" v-model="results[index]">
                                <label for="one">{{ option.label }} </label>
                            </div>
                        </div>
                    </div>
                </b-col>
                <b-col class="recipe">
                    <h3>Recipe Area</h3>

    {{ spreadResult }} {{ biteResult }}
                </b-col>

            </b-row>

        </b-container>
    </div>

    <!-- <div class="recipe">

</div> -->


</div>
</template>

<style scoped>
.header {
    text-align: center;
    padding: 20px;
    margin-top: 30px;
}

.recipe {
    background-color: rgb(153, 214, 214);
}

h3 {
    font-size: 20px;
}

.recipe h3{
    padding-top: 30px;
}

h4 {
    font-size: 14px;
}

label {
    font-size: 16px;
}

.text{
    margin: 5px;
}

#form {
    display: flex;
    flex-direction: column;
    padding: 30px;
    background-color: #eeeeee;
}

.panel {
    display: flex;
    flex-direction: row;
    align-items: center;
    position: relative;
    margin: 10px;
    /* border: solid 2px #dddddd; */
    padding: 20px;
    background-color: white;
}

input[type="radio"] {
    /* display: none; */
}

.cardRow .cardBtn label {
    display: block;
    border: 2px solid #bbbbbb;
    text-align: center;
    padding: 15px;
}

.cardRow .cardBtn .title {
    font-size: 18px;
    color: black;
    padding: 40px;
    font-weight: 600;
}

.cardRow .cardBtn label:hover {
    border: 2px solid #bbbbbb;
    background: #8eacd4;
}

.cardRow .cardBtn input:checked+label {
    background: #8eacd4;
    border: 2px solid #777777;
}

.cardRow .cardBtn input:checked+label .title {
    color: #eee;
}
</style>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
export default {
    name: 'Home',
    data() {
        return {
            categories: [
                {
                    name: 'Spread',
                    id: 'spread',
                    description: 'The way a cookie expands and settles while baking',
                    options: [{
                            label: "Wide",
                            value: "wide",
                            imgUrl: "https://unsplash.com/photos/DqvMdSbWlBE"
                        },
                        {
                            label: "Compact",
                            value: "compact",
                            imgUrl: ""
                        },
                    ],
                },
                {
                    name: 'Tenderness',
                    id: 'tenderness',
                    description: 'Heirloom biodiesel quinoa mlkshk asymmetrical master cleanse affogato blog marfa chillwave semiotics gastropub',
                    imgUrl: "",
                    options: [{
                            label: "Crunchy",
                            value: "crunchy",
                            imgUrl: ""
                        },
                        {
                            label: "Soft",
                            value: "soft",
                            imgUrl: ""
                        },
                    ],
                },
                {
                    name: 'Rise',
                    id: 'rise',
                    description: 'Offal waistcoat occupy humblebrag pinterest, pour-over food truck bitters.',
                    imgUrl: "",
                    options: [{
                            label: "Mound",
                            value: "mound",
                            imgUrl: ""
                        },
                        {
                            label: "Thin",
                            value: "thin",
                            imgUrl: ""
                        },
                    ],
                },
                {
                    name: 'Texture',
                    id: 'texture',
                    description: 'Banjo flannel pour-over fixie twee humblebrag.',
                    imgUrl: "",
                    options: [{
                            label: "Fudgy",
                            value: "fudgy",
                            imgUrl: ""
                        },
                        {
                            label: "Cakey",
                            value: "cakey",
                            imgUrl: ""
                        },
                    ],
                },
                {
                    name: 'Chocolate',
                    id: 'chocolate',
                    description: 'Mixtape edison bulb tattooed blog, brunch seitan live-edge plaid forage',
                    imgUrl: "",
                    options: [{
                            label: "Small Chunks",
                            value: "small",
                            imgUrl: ""
                        },
                        {
                            label: "Large Chunks",
                            value: "large",
                            imgUrl: ""
                        },
                        {
                            label: "Swirled In",
                            value: "swirled",
                            imgUrl: ""
                        },
                    ],
                },
                {
                    name: 'Flavor',
                    id: 'flavor',
                    description: 'Sartorial single-origin coffee VHS green juice salvia.',
                    imgUrl: "",
                    options: [{
                            label: "Dark, toffee",
                            value: "dark",
                            imgUrl: ""
                        },
                        {
                            label: "Light, milky",
                            value: "light",
                            imgUrl: ""
                        },
                    ],
                },
            ],
            results: []
        }
    },
    computed: {
        spreadResult() {
            return this.results
        },
        // biteResult() {
        //     return this.results[1]
        // }
    },
    methods: {
        onDeleteLastItem() {
            this.exampleList.pop();
        }
    },
    components: {
        HelloWorld
    },
};
</script>
