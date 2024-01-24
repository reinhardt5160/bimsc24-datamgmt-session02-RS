<!-- the script is where the js code goes -->
<script>
import { ref } from "vue" // you need this to use ref()


</script>



<!-- the template is where the html code goes -->
<template>

    <div id="navbar" class="container">  
            
        <div id="title">Reinhardt's newest website</div>
            <!-- <div id="logo">
                <img src="cow.jpg" alt="macad cow"> -->

            <!-- </div> -->
            
        </div>

        <div id="flex">

            <div id="sidebar" class="container"> Sidebar </div>

            <div id="main" class="container"> What the cow said </div>

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
        border-color: red;
        text-align: center;
        vertical-align:baseline;
        font-size: 25px;
    }

    #flex{
        
        display: flex;
        height: calc(100vh - 50px);
    }

    #sidebar{
        
        width:30%;
        border-color: blue;

    }

    #main{
        width:70%;
        border-color: green;

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
        border-width: 1px;

    }

</style>