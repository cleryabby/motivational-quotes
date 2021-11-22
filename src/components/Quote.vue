
<template>
  <div class="main">
    <div id="motivateBtn">
        
    <button v-on:click="getData">Get Motivated</button>
    </div>
    <div id="motivationalQuote">{{ motivationalQuote.text }} <br> 
    <div id="author">
    {{motivationalQuote.author}} 
    </div>
    </div>
  </div>
</template>

<script>
export default {
    name: 'Quote',

    data() {
        return {
            motivationalQuote: {
                author: "",
                text: ""
      },
        }
    },
      methods: {
    getData(){
      fetch("https://type.fit/api/quotes")
  .then((response) => {
    return response.json();
   
    
  })
  .then((data) => {
    
    const quotes = data;
    const keys = Object.keys(quotes);
    console.log(keys);
    const randIndex = Math.floor(Math.random() * keys.length);
    const randKey = keys[randIndex];
    console.log(randKey);
    const quote = quotes[randKey];
    console.log(quote);
    this.motivationalQuote = quote;
    
  });
  
}
      },
  computed: {
    
  }
};

</script>

<style scoped>

#motivationalQuote {
font-size: 40px;
color: #280c60;
margin-top: 20px;
font-weight: bold;
width: 70%;
margin-left: auto;
margin-right: auto;

}

#author {

font-weight: normal;
}

button {

background-color: #280c60;
color: #e8e8ef;
font-size: 35px;
border: solid #8e8ebf 10px;
border-radius: 10px;
padding: 8px;

}
</style>