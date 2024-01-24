<!-- the script is where the js code goes -->
<script setup>
import { ref } from "vue";

// Define variables and constants
let count = ref(0);

// Define functions
function increment() {
  count.value++;
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

            </div>



            <div id="main" class="container"> What the philosopher cow said 
                <p style="margin-left: 8px">Count is: {{ count }}</p>

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

</style>