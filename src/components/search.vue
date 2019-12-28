<template>
	
	<div class="search">
		
	
		<br><h5><input type="text" name="haberSearchtittle" placeholder="Enter Film Name" v-model="query" @keypress.enter="handleSearch"><br/></h5>

		<br><h5><input type="text" name="haberSearchyear" placeholder="Enter year of realese" v-model="query2" @keypress.enter="handleSearch"><br/></h5>
		<h5><button v-on:click="handleSearch">Search</button></h5>
		
	</div>
</template>


<script>
	export default{
		data(){
			return{

				query:'',
				query2:''
				

			}
		},

	
	methods:{
		handleSearch(){
			if (this.query=="") {	
				alert("enter film tittle");
			
			}else if (this.query2==""){
				alert("enter year of realese")
			}
			else{
				this.$emit('SearchRequested', this.query, this.query2);
			}
		}
		
	
	}
}

</script>

<style> 
	.search input{
		padding: 15px;
		width: 400px;
		border-radius: 20px;	


	}
	.search button{
		padding: 15px;
		width: 115px;
		border-radius: 20px;
		background-color:#778899;
		color:black;
	}


</style>