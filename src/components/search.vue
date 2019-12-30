<template>
	
	<div class="search">
		
	
		<br><h5><input type="text" name="Searchtittle" placeholder="Enter Film Name" v-model="query" @keypress.enter="handleSearch"><br/></h5>

		<br><h5><input type="text" name="Searchyear" placeholder="Enter year of realese" v-model="query2" @keypress.enter="handleSearch"><br/></h5>
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
			
			}else{
				this.$emit('SearchRequested', this.query, this.query2);
			}
		}
		
	
	}
}

</script>

<style> 
	.search input{
		min-width: 300px;
		max-width: 500px;
		border-radius: 20px;	
		border: 0px;
		padding: 5px 5px;
		
		border: 2px solid #CF5C3F;
	overflow: auto;
	border-radius: 5px;
	-moz-border-radius: 5px;
	-webkit-border-radius: 5px;


	}
	
	.search button{
		padding: 15px;
		width: 115px;
		border-radius: 20px;
		background-color:#778899;
		color:black;
		border: 2px solid #CF5C3F;
	}

@media only screen and (min-width : 150px) and (max-width : 780px)
{
	
	.search
	{
		width: 95%;
		margin: 0 auto;
	}

}


</style>