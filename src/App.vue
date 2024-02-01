<!-- the script is where the js code goes -->
<script setup>
import { ref } from "vue";
import { MagicString } from "vue/compiler-sfc";

// Define variables and constants
let count = ref(0);

// Define functions
function increment() {
  count.value++;
}

// Function for random quote
let textList = ref([
  '"The greatness of a nation and its moral progress can be judged by the way its animals are treated." — Mahatma Gandhi',
  '"Until one has loved an animal, a part of ones soul remains unawakened." — Anatole France',
  '"The question is not, Can they reason? nor, Can they talk? but rather, Can they suffer? — Jeremy Bentham',
  '"The more I learn about people, the more I like my dog." — Mark Twain',
  '"We can judge the heart of a man by his treatment of animals." — Immanuel Kant',
  '"The world is a dangerous place, not because of those who do evil, but because of those who look on and do nothing." — Albert Einstein',
  '"The greatness of a community is most accurately measured by the compassionate actions of its members." — Coretta Scott King',
  '"In the eyes of a cat, all things belong to cats." — English Proverb',
  '"Animals are such agreeable friends—they ask no questions; they pass no criticisms." — George Eliot',
  '"The soul is the same in all living creatures, although the body of each is different." — Hippocrates'
]);

let randomText = ref('');

let pickRandomText = () => {
  randomText.value = getRandomText(textList.value);
};

let getRandomText = (textList) => {
  let randomIndex = Math.floor(Math.random() * textList.length); //get random index for a range b/w o and list length of textList
  return textList[randomIndex]; //call text by index
};


// Color try definition
let newColor = ref('');

// Color try function
function pickColor() {
  const doc = document.documentElement;
//   doc.style.background = newColor.value;
  const main = document.querySelector("#main");
  main.style.background = newColor.value;
  console.log(newColor.value);
}


</script>

<!-- the template is where the html code goes -->
<template>

    <div id="navbar" class="container">  
            
        <div id="title">Reinhardt's newest website</div>
            <div id="logo">
                <img src="./assets/cow.jpg" alt="macad cow">

            </div>
            
        </div>

        <div id="flex">

            <div id="sidebar" class="container"> Sidebar 
                <button @click="increment">Add one more</button>
                <button @click="pickRandomText">Say something smart</button>

                <!-- color script try -->
                <input type="text" id="textInput" v-model = "newColor" placeholder="Your favorite color">
                <button @click="pickColor">Apply new color</button>
            </div>

            <div id="main" class="container"> Outputs
                <p class="outputs" style="margin-left: 8px">Count is: {{ count }}</p>
                <p class="outputs" style="margin-left: 8px" v-if="randomText"> Philosoher cow says {{ randomText }}</p>
            </div>

        </div>

</template>



<!-- style is where the css code goes -->
<style scoped>

    body{

        margin:0;
    }

    div{

        /* put the borders in the inside of container */
        box-sizing: border-box;
    }

    img{

        height: 100%;
        width: auto;

    }

    #navbar{

        height: 50px;
        border-color: white;
        text-align: left;
        vertical-align:bottom;
        font-size: 30px;
    }

    #flex{

        display: flex;
        height: calc(100vh - 50px);
    }

    #sidebar{

        font-size: 22px;
        width:30%;
        border-color: black;

    }

    #main{

        font-size: 22px;
        width:70%;
        border-color: black;

    }

    #title{

        width: 70%;
        float:left;
        
    }

    #logo{
        width: 30%;
        height: 100%;
        float:right;
        text-align: right;

    }

    .container{

        border-style: dotted;
        border-width: 2px;

    }

    .outputs{

        font-style: italic;

    }


</style>