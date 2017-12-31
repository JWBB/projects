<template>
  <div id="translateOutTo">
  		<h2>{{translatedText}}</h2>
  </div>
</template>

<script>


export default {
  name: 'translateOutTo',
  props:[
  	"translatedText"
  ]
 
}
</script>

<style>
#text{
	font-size:20px ;
	
}
</style>
