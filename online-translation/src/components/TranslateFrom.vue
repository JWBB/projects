<template>
  <div id="translateFrom">
  	<div>
  		<form class="form-inline" id="transform">
  			<input class="form-control" type="text" v-model="textTranslate" placeholder="输入需要翻译的内容"/>
  			<select v-model="language" class="form-control">
  				<option value="en">English</option>
  				<option value="ru">Russian</option>
  				<option value="ko">Korean</option>
  				<option value="ja">Janpenese</option>
  			</select>
  			<button type="button" value="翻译" v-on:click="formSubmit" class="btn btn-primary">翻译</button>
 		 </form>
  	</div>
  
  </div>
</template>

<script>


export default {
  name: 'translateFrom',
  data:function(){
  	return{
  		textTranslate:"",
  		language:""
  	}
  },
  methods:{
  	formSubmit:function(e){
//		alert(this.textTranslate);
		this.$emit("formSubmit",this.textTranslate,this.language);
  		//消除默认事件
  		e.preventDefault();
  	}
  },
  created:function(){
  	this.language="en";
  }
}
</script>

<style>

#transform{
	border: 1px solid #fff;
	border-radius: 10px;
	text-align: center;
	width: 425px;
	margin: 0 auto;
}
</style>
