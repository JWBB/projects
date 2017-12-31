<template>
  <div id="app">
  <h1>在线翻译</h1>
  <h5 class="text-muted">简单/易用/便捷</h5>
   <translateFrom v-on:formSubmit="translateText"></translateFrom>
   <translateOutTo v-text="translatedText" id="text"></translateOutTo>
  </div>
</template>

<script>
import TranslateFrom from './components/TranslateFrom'
import TranslateOutTo from './components/TranslateOutTo'
export default {
  name: 'app',
  data:function(){
  	return{
  		translatedText:""
  	}
  },
  components: {
    TranslateFrom,TranslateOutTo
    
  },
  methods:{
  	translateText:function(text,language){
//		alert(text);
			this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20171231T125329Z.693db322bbb3ec2a.166ebc398eeb225806c420076e9eeae680e2f43a&lang='+language+'&text='+text)
			.then((response)=>{
//				console.log(response.body.text[0])
					this.translatedText=response.body.text[0]
			})
  	}
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#text{
	margin: 20px 0 0 0;
}
</style>
