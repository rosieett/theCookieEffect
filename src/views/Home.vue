<template>
<div class="home">
    <!-- <hello-world />
     <div id="form">
        <div v-for="(category, index) in categories">
            <h3>{{ category.name }}</h3>
            <h4>{{ category.description }}</h4>
            <div v-for="option in category.options">
                <input type="radio" :name="category.id" id="one" v-bind:value="option.value" v-model="results[index]">
                <label for="one">{{ option.label }}</label>
            </div>
        </div>
    </div>

    {{ results }} {{ biteResult }} -->

    <div id="form">

        <div class="headers" v-for="(category, index) in categories">
            <div class="section">
                <h3>{{ category.name }}</h3>
                <h4>{{ category.description }}</h4>

                <b-container class="bv-example-row cardRow">
                    <b-row>
                        <b-col class="cardBtn" v-for="option in category.options">

                            <input type="radio" :name="category.id" id="one" v-bind:value="option.value" v-model="results[index]">
                            <label for="one">{{ option.label }} </label>
                        </b-col>
                    </b-row>
                </b-container>
            </div>
        </div>
    </div>

    {{ spreadResult }} {{ biteResult }}

</div>

</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
export default {
    name: 'Home',
    data() {
        return {
            categories: [{
                    name: 'Spread',
                    id: 'spread',
                    description: 'The way a cookie expands and settles while baking',
                    options: [{
                            label: "Wide",
                            value: "wide",
                            imgUrl:"https://unsplash.com/photos/DqvMdSbWlBE"
                        },
                        {
                            label: "Compact",
                            value: "compact",
                            imgUrl: ""
                        },
                    ],
                },
                {
                    name: 'Bite',
                    id: 'bite',
                    description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
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
            ],
            results: []
        }
    },
    computed: {
        spreadResult() {
            return this.results[0]
        },
        biteResult() {
            return this.results[1]
        }
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

<style scoped>
.home {
    background-color: lightgoldenrodyellow;
    padding: 20px;
}

.home .hello {
    background-color: darkgray;
}


#form {
    display: flex;
    flex-direction: column;
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    width: 60%;
    padding: 30px;
    /* background-color: #cccccc; */
}

.section {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    position: relative;
    margin: 30px;
    border: solid 2px #dddddd;
    padding: 20px;
}


.cardRow .cardBtn input{
    /* display: none; */
}

.cardRow .cardBtn label{
    display: block;
    border: 3px solid #b3cbeb;
    text-align: center;
    padding: 35px;
}

.cardRow .cardBtn .title{
    font-size: 18px;
    color: black;
    padding: 40px;
    font-weight: 600;
}

.cardRow .cardBtn label:hover{
    border: 2px solid gray;
    background: #ccc;
}

.cardRow .cardBtn input:checked + label {
    background: #8eacd4;
}


.cardRow .cardBtn input:checked + label .title {
    color: #eee;
}

</style>
